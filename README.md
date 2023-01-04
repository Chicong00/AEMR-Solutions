# AEMR-Solutions
💻 Work performed on Azure Data Studio 💻
## Part 1: Energy Stability and Markert Outages
###  1. What are the most common outage types?
````sql
SELECT
    Reason,
    Start_Year,
    count(1) total_number_outage_events
from dbo.aemo
where status = 'Approved' 
GROUP by Start_Year, Reason, [Status]
Order by Start_Year, total_number_outage_events DESC
````
|Reason|Start_Year|total_number_outage_events|
|---|---|---|
|Forced|2016|1264|
|Scheduled (Planned)	|2016|380|
|Consequential|2016|1264|
|Opportunistic Maintenance (Planned)|2016|181|
|Forced|2017|1622|
|Scheduled (Planned)|2017|320|
|Consequential|2017|127|
|Opportunistic Maintenance (Planned)|2017|102|
### 2. How frequently do outages occur?
````sql
SELECT
    Reason,
    Start_Year YEAR,
    Start_Month month,
    count(1) total_number_outage_events
from dbo.AEMO
WHERE status = 'Approved'
GROUP by Start_Year,Start_Month, Reason
order by Reason,[YEAR], [month]
````
|Reason|YEAR|month|total_number_outage_events|
|---|---|---|---|
|Consequential	|2016	|1	|24|
|Consequential	|2016	|2	|23|
|Consequential	|2016	|3	|7|
|Consequential	|2016	|5	|36|
|Consequential	|2016	|6	|12|
|Consequential	|2016	|7	|23|
|Consequential	|2016	|8	|6|
|Consequential	|2016	|9	|1|
|Consequential	|2016	|10	|15|
|Consequential	|2016	|11	|25|
|Consequential	|2016	|12	|9|
|Consequential	|2017	|1	|12|
|Consequential	|2017	|2	|27|
|Consequential	|2017	|3	|19|
|Consequential	|2017	|4	|12|
|Consequential	|2017	|5	|5|
|Consequential	|2017	|6	|8|
|Consequential	|2017	|7	|1|
|Consequential	|2017	|8	|2|
|Consequential	|2017	|9	|10|
|Consequential	|2017	|10	|11|
|Consequential	|2017	|11	|9|
|Consequential	|2017	|12	|11|
|Forced	|2016	|1	|134|
|Forced	|2016	|2	|149|
|Forced	|2016	|3	|94|
|Forced	|2016	|4	|87|
|Forced	|2016	|5	|100|
|Forced	|2016	|6	|113|
|Forced	|2016	|7	|79|
|Forced	|2016	|8	|152|
|Forced	|2016	|9	|96|
|Forced	|2016	|10	|67|
|Forced	|2016	|11	|127|
|Forced	|2016	|12	|66|
|Forced	|2017	|1	|70|
|Forced	|2017	|2	|97|
|Forced	|2017	|3	|53|
|Forced	|2017	|4	|73|
|Forced	|2017	|5	|109|
|Forced	|2017	|6	|168|
|Forced	|2017	|7	|183|
|Forced	|2017	|8	|173|
|Forced	|2017	|9	|133|
|Forced	|2017	|10	|207|
|Forced	|2017	|11	|146|
|Forced	|2017	|12	|210|
|Opportunistic Maintenance (Planned)|	2016	|1	|9|
|Opportunistic Maintenance (Planned)|	2016	|2	|12|
|Opportunistic Maintenance (Planned)|	2016	|3	|14|
|Opportunistic Maintenance (Planned)|	2016	|4	|3|
|Opportunistic Maintenance (Planned)|	2016	|5	|4|
|Opportunistic Maintenance (Planned)|	2016	|6	|14|
|Opportunistic Maintenance (Planned)|	2016	|7	|13|
|Opportunistic Maintenance (Planned)|	2016	|8	|7|
|Opportunistic Maintenance (Planned)|	2016	|9	|11|
|Opportunistic Maintenance (Planned)|	2016	|10	|5|
|Opportunistic Maintenance (Planned)|	2016	|11	|7|
|Opportunistic Maintenance (Planned)|	2016	|12	|7|
|Opportunistic Maintenance (Planned)|	2017	|1	|9|
|Opportunistic Maintenance (Planned)|	2017	|2	|6|
|Opportunistic Maintenance (Planned)|	2017	|3	|7|
|Opportunistic Maintenance (Planned)|	2017	|4	|8|
|Opportunistic Maintenance (Planned)|	2017	|5	|9|
|Opportunistic Maintenance (Planned)|	2017	|6	|7|
|Opportunistic Maintenance (Planned)|	2017	|7	|5|
|Opportunistic Maintenance (Planned)|	2017	|8	|14|
|Opportunistic Maintenance (Planned)|	2017	|9	|7|
|Opportunistic Maintenance (Planned)|	2017	|10	|8|
|Opportunistic Maintenance (Planned)|	2017	|11	|16|
|Opportunistic Maintenance (Planned)|	2017	|12	|6|
|Scheduled (Planned)	|2016	|1	|24|
|Scheduled (Planned)	|2016	|2	|43|
|Scheduled (Planned)	|2016	|3	|21|
|Scheduled (Planned)	|2016	|4	|45|
|Scheduled (Planned)	|2016	|5	|33|
|Scheduled (Planned)	|2016	|6	|30|
|Scheduled (Planned)	|2016	|7	|31|
|Scheduled (Planned)	|2016	|8	|29|
|Scheduled (Planned)	|2016	|9	|16|
|Scheduled (Planned)	|2016	|10	|37|
|Scheduled (Planned)	|2016	|11	|41|
|Scheduled (Planned)	|2016	|12	|30|
|Scheduled (Planned)	|2017	|1	|12|
|Scheduled (Planned)	|2017	|2	|20|
|Scheduled (Planned)	|2017	|3	|30|
|Scheduled (Planned)	|2017	|4	|34|
|Scheduled (Planned)	|2017	|5	|47|
|Scheduled (Planned)	|2017	|6	|17|
|Scheduled (Planned)	|2017	|7	|22|
|Scheduled (Planned)	|2017	|8	|23|
|Scheduled (Planned)	|2017	|9	|18|
|Scheduled (Planned)	|2017	|10	|50|
|Scheduled (Planned)	|2017	|11	|27|
|Scheduled (Planned)	|2017	|12	|20|

### 3. Are there any energy providers that have more outages than their peers which may indicate that these providers are unreliable?
````sql
select
    Participant_Code,
    Start_Year YEAR,
    count(1) total_number_outage_events,
    ROUND(AVG(CONVERT(float,DATEDIFF(MINUTE, Start_Time, End_Time)/60)/24),2) Avg_days_outage_duration
from dbo.AEMO 
WHERE [Status]='Approved'
GROUP by Participant_Code, Start_Year
order by Participant_Code, [YEAR], Avg_days_outage_duration
````
|Participant_Code|YEAR|total_number_outage_events|Avg_days_outage_duration|
|---|---|---|---|
|AURICON	|2016	|298	|0.07|
|AURICON	|2017	|577	|0.08|
|AUXC	|2016	|209	|0.08|
|AUXC	|2017	|122	|0.01|
|COLLGAR	|2016	|53	|0.40|
|COLLGAR	|2017	|64	|0.98|
|DNHR	|2016	|12	|0.40|
|DNHR	|2017	|13	|0.48|
|ENRG	|2016	|69	|15.71|
|ENRG	|2017	|54	|4.19|
|EUCT	|2016	|28	|9.75|
|EUCT	|2017	|17	|0.03|
|GW	|2016	|402	|0.26|
|GW	|2017	|270	|0.88|
|KORL	|2016	|87	|0.34|
|KORL	|2017	|108	|0.55|
|MCG	|2016	|4	|1.29|
|MCG	|2017	|18	|0.23|
|MELK	|2016	|273	|0.28|
|MELK	|2017	|263	|4.82|
|MUND	|2016	|30	|0.49|
|MUND	|2017	|31	|0.19|
|PJRH	|2016	|142	|0.31|
|PJRH	|2017	|146	|0.44|
|PMC	|2016	|107	|0.32|
|PMC	|2017	|61	|0.|03|
|PUG	|2016	|47	|0.92|
|PUG	|2017	|149	|0.18|
|STHRNCRS	|2016	|35	|0.33|
|STHRNCRS	|2017	|35	|0.21|
|TSLA_MGT	|2016	|71	|0.25|
|TSLA_MGT	|2017	|176	|0.31|
|TRMOS	|2016	|55|	0.18|
|TRMOS	|2017	|55|	0.04|
|WGUTD	|2016	|9|	0.02|
|WGUTD	|2017	|12	|0.58|

## Part 2: Energy Losses and Market Reliability
### 1. Of the outage types in 2016 and 2017, what percent were forced outages?
````sql
with forced_outage as
( select 
    Start_Year,
    count(1) total_no_Forced_outage_events 
  from dbo.AEMO WHERE Reason = 'Forced' and [Status] = 'Approved' 
  GROUP by Start_Year),
total as
( select 
    Start_Year,
     COUNT(1) total_no_outage_events 
  from dbo.AEMO where [Status] = 'Approved' 
  GROUP by Start_Year)
 
SELECT
    f.Start_year, 
    total_no_Forced_outage_events, 
    total_no_outage_events,
    convert(float,round(100.0*total_no_Forced_outage_events/total_no_outage_events,2)) Forced_outage_Percentage
FROM forced_outage f 
JOIN total t 
on f.start_year = t.start_year
````
|Start_year|total_no_Forced_outage_events|total_no_outage_events|Forced_outage_Percentage|
|---|---|---|---|
|2016	|1264	|1931	|65.46|
|2017	|1622	|2171	|74.71|

### 2. What was the average duration for each outage during both 2016 and 2017? Have we seen an increase in the average duration of each outage?
````sql
SELECT
    Reason,
    start_year year, 
    count(reason) total_number_outage_events,
    round(avg(outage_mw),2) Avg_Outage_MW_Loss,
    convert(float,round(DATEDIFF(MINUTE,Start_Time,End_Time),2)) as avg_mins_outage_duration
FROM dbo.AEMO
WHERE  [Status]='Approved'
group by reason, start_year 
order by Reason, [year]
````
|Reason|year|total_number_outage_events|Avg_Outage_MW_Loss|avg_mins_outage_duration|
|---|---|---|---|---|
|Consequential	|2016	|181	|53,06	|518.78|
|Consequential	|2017	|127	|51,03	|481.89|
|Forced	|2016	|1264	|55,62	|812.92|
|Forced	|2017	|1622	|50,56	|1144.09|
|Opportunistic Maintenance (Planned)	|2016	|106	|103,66	|456.51|
|Opportunistic Maintenance (Planned)	|2017	|102	|84,4	|387.35|
|Scheduled (Planned)	|2016	|380	|99,1	|6582.32|
|Scheduled (Planned)	|2017	|320	|85,47	|8034.75|

### 3. Which energy providers tended to be the most unreliable?
````sql
--3.1 Calculate the AVERAGE duration and AVERAGE energy lost (MW) for all approved outages where the reason is equal to Forced for each participant code
 
select
    Participant_Code,
    Start_Year YEAR,
    round(avg(Outage_MW),2) Avg_Outage_MW_Loss,
  convert(float,round(DATEDIFF(MINUTE,Start_Year,End_Year)/(60*24),2)) avg_outage_duration_time_days
from dbo.AEMO
WHERE Reason = 'Forced'and [Status]='Approved'
group by reason, start_year 
order by Reason, [year]
````
|Participant_Code|YEAR|Avg_Outage_MW_Loss|Average_Outage_Duration_Time_Days|
|---|---|---|---|
|AURICON	|2016	|51,42	|0.07|
|AURICON	|2017	|44,16	|0.08|
|AUXC|	2016	|13,27	|0.08|
|AUXC|	2017	|14,74	|0.01|
|COLLGAR|	2016	|149	|0.40|
|COLLGAR|	2017	|61,93	|0.98|
|DNHR	|2016	|1,44	|0.40|
|DNHR	|2017	|1,44	|0.48|
|ENRG	|2016	|56,32	|15.71|
|ENRG	|2017	|27,41	|4.19|
|EUCT	|2016	|5,89	|9.75|
|EUCT	|2017	|21,6	|0.03|
|GW|	2016|	49,69|	0.26|
|GW|	2017|	85,14|	0.88|
|KORL	|2016|	76,23	|0.34|
|KORL	|2017|	61,57	|0.55|
|MCG	|2016|	55	|1.29|
|MCG	|2017|	46,94	|0.23|
|MELK	|2016|	87,71	|0.28|
|MELK	|2017|	58,11	|4.82|
|MUND	|2016|	36,8	|0.49|
|MUND	|2017|	26,57	|0.19|
|PJRH	|2016|	72,61	|0.31|
|PJRH	|2017|	67,21	|0.44|
|PMC	|2016|	131,78	|0.32|
|PMC	|2017|	141,21	|0.03|
|PUG	|2016|	33,98	|0.92|
|PUG	|2017|	30,46	|0.18|
|STHRNCRS	|2016|	23	|0.33|
|STHRNCRS	|2017|	16,26	|0.21|
|TRMOS	|2016	|18,96	|0.25|
|TRMOS	|2017	|29,17	|0.31|
|TSLA_MGT	|2016	|80	|0.18|
|TSLA_MGT	|2017	|42,48	|0.04|
|WGUTD	|2016	|27	|0.02|
|WGUTD	|2017	|27,66	|0.58|

````sql
--3.2 Calculate the Average Outage (MW) Loss and Overall Summed Outage (MW) loss for each participant code where the Status is Approved and the Outage Reason is Forced across both 2016 and 2017.
 
SELECT
    Participant_Code,
    Start_Year Year,
    round(AVG(Outage_MW),2) Avg_Outage_MW_Loss,
    round(SUM(Outage_MW),2) Overall_Summed_Outage
from dbo.AEMO
WHERE [Status] ='Approved' and Reason = 'Forced'
GROUP by Participant_Code, Start_Year
orderby [Year],Participant_Code
````
|Participant_Code|Year|Avg_Outage_MW_Loss|Overall_Summed_Outage|
|---|---|---|---|				
|AURICON	|2016	|51,42	|10696,28|
|AUXC	|2016	|13,27	|2734,14|
|COLLGAR	|2016	|149	|4320,86|
|DNHR	|2016	|1,44	|1,44|
|ENRG	|2016	|56,32	|1182,8|
|EUCT	|2016	|5,89	|64,8|
|GW	|2016	|49,69	|15751,38|
|KORL	|2016	|76,23	|4040,32|
|MCG	|2016	|55	|55|
|MELK	|2016	|87,71	|13771,07|
|MUND	|2016	|36,8	|147,2|
|PJRH	|2016	|72,61	|5881,52|
|PMC	|2016	|131,78	|9093,08|
|PUG	|2016	|33,98	|815,47|
|STHRNCRS	|2016	|23	|299|
|TRMOS	|2016	|18,96	|1232,43|
|TSLA_MGT	|2016	|80	|160|
|WGUTD	|2016	|27	|54|
|AURICON	|2017	|44,16	|21639,55|
|AUXC	|2017	|14,74	|1768,76|
|COLLGAR	|2017	|61,93	|2787,06|
|DNHR	|2017	|1,44	|1,44|
|ENRG	|2017	|27,41	|191,86|
|EUCT	|2017	|21,6	|64,8|
|GW	|2017	|85,14	|19326,56|
|KORL	|2017	|61,57	|4679,68|
|MCG	|2017	|46,94	|563,33|
|MELK	|2017	|58,11	|10285,4|
|MUND	|2017	|26,57	|398,58|
|PJRH	|2017	|67,21	|4839,28|
|PMC	|2017	|141,21	|5648,44|
|PUG	|2017	|30,46	|4112,1|
|STHRNCRS	|2017	|16,26	|292,7|
|TRMOS	|2017	|29,17	|5016,67|
|TSLA_MGT	|2017	|42,48	|169,9|
|WGUTD	|2017	|27,66	|221,29|
