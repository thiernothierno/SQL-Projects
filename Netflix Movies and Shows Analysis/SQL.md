### Table Initialization
```
create table netflix
(
show_id varchar(10),
type varchar(10),
title varchar(150),
director varchar(250),
casting_names varchar(900),
county varchar(150),
date_added varchar(50),
releasing_year int,
rating varchar(15),
duration varchar(15),
listed_in varchar(100),
description varchar(300)

)
```
### 1 : Count the number of Movies vs TV Shows
```
select type, count(show_id) as Total_Count from netflix group by 1
```

### 2 : Find the most common rating for movies and TV shows
```
select rating, type from
(
    select rating, type, count(*), rank() over(partition by type order by count(*) desc) as new_field
    from netflix 
    group by rating, type
) as t where new_field = 1
```

### 3 : List all movies released in a specific year (e.g.. 2021)
```
select * from netflix where type = 'Movie' and releasing_year = 2021;
```
### 4 : Find the top 5 countries with the most content on Netflix

```
select
  unnest(string_to_array(country, ',')) as new_country, count(show_id) as Total_Count
from netflix group by 1 order by 2 desc limit 5
```

### 5 : Identify the longest movie or TV show duration
```
select * from netflix where type = 'Movie' and duration = (select max(duration) from netflix)
```
### 6 : Find content added in the last 5 years
```
select * 
from netflix
where to_date(date_added, 'Month DD, YYYY') >= current_date - interval'5 years'
```

### 7 : Find all the movies and TV Shows by director 'Haile Gerima'
```
select * from netflix where director Ilike '%Haile Gerima%'
```

### 8 : Count the number of content items in each genre
```
select unnest(string_to_array(listed_in,',')) as genre, count(show_id) as Total_Count 
from netflix
group by 1
order by 2 desc
```

### 9 : List all TV Shows with more than 5 seasons
```
select * from netflix where type = 'TV Show' and split_part(duration, ' ', 1)::numeric > 5

```

### 10 : Find each year and the average numbers of content release by United States on netflix
### Return top 5 years wiht highest avg content release.
```
select 
extract(year from to_date(date_added, 'Month DD, YYYY')) as date, 
count(*) as Total_Count,
round(count(*)::numeric / (select count(*) from netflix where country = 'India') * 100::numeric, 2) as average
from netflix
where country = 'United States'
group by 1
order by 3 desc
limit 5
```

### 11 : List all movies that are documentaries
```
select * from netflix where listed_in ilike '%documentaries%'
```

### 12 : Find all content without director
```
select * from netflix where director is Null
```

### 13 : Find how many movies actor 'Salman Khan' appears in last 10 years
```
select * from netflix where type = 'Movie' 
and casting_names ilike '%salman khan%'
and releasing_year > extract(year from current_date) - 10

```

### 14 : Find the top 10 actors who have appeared in the highest number of movies produced in India.
```
select unnest(string_to_array(casting_names, ',')) as actors,
count(*) as Total_Count 
from netflix
where country ilike '%India%'
group by 1
order by 2 desc
limit 10
```

### 15 : Categorize the content based on the presence of the keywords 'kill' and 'violence'
### in the description field. Label content containing these keywords as 'Bad' and all other 
### content as 'Good'. Count how many items fall into each category. 
```'
with des as (
select 
	case
		when description ilike '%kill%' or description ilike '%violence%' then 'Bad'
		else 'Good'
	end as res
from netflix ) select res, count(*) from des group by 1
```

