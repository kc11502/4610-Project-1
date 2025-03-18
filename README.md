# Team 4 MIST 4610 Group Project 1

# TEAM NAME
21482 Group 4 


# TEAM MEMBERS
- Jennifer Lee [@jcnniferlee](https://github.com/jcnniferlee/MIST4610GroupProject1.git)
- Connie Wang [@cw76668](https://github.com/cw76668)
- Kevin Choi [@kc11502](https://github.com/kc11502)
- Kayla Valentine [kaylavalentine](https://github.com/kaylavalentine)
- Vivek Shah [vsshah5](https://github.com/vsshah5)

# SCENARIO DESCRIPTION
The scenario at hand is to design and implement a relational database that enables a large music conglomerate to efficiently manage its multiple record labels. The primary entity in the system is the Record Label, as each label operates under the conglomerate by signing artists, managing music releases, overseeing concerts, and handling various revenue streams such as ticketing and royalties. Each record label functions as an independent entity within the conglomerate and these labels work hand in hand with streaming platforms, concert venues, and distribution networks to promote artsts and maximize revenue. By establishing a well structured database, the system allows stakeholders to track artist success, label performance, and financial efficiency in real-time. Our focus is to accurately represent these relationships within the database and populate the system with sample data, allowing us to perform functional queries that may provide us with valuable business insight about the conglomerate. 


# DATA MODEL
![Image](https://github.com/user-attachments/assets/57884c27-fff6-4e3d-8843-a32be7eaca14)
Our data model represents the structure and operations of a large music conglomerate that owns multiple record labels. The **RecordLabel** entity is the core of the database and stores information about the individual record labels such as their name, founding year, and CEO. This has a one-to-many relationship with Contract as record labels can have many contracts with different artists. **Contract** defines the agreement between an artist and their corresponding record labels, specifying things like record revenue share and type.

<p align="center"> ────୨ৎ────

The **Artist** entity contains information about the artists, such as their name, date of birth, and debut year. Artists can have many contracts, which is shown by the one-to-many relationship between the two. Artists also has a one-to-many relationship with awards as they can win multiple awards that help them gain more industry recognition. The **Awards** entity contains information about various rewards such as their name, category, and year. A one-to-many relationship also exists between Artists and the **Royalty** entity, which contains the royalty percentage share and amount. This is the percentage of revenue an artist earns from streaming, album sales, and concert performances. 

<p align="center"> ────୨ৎ────

Our model also features an **Album** entity, which includes the title, release date, and genre. This has a one-to-many relationship with Artist as well as artists can release multiple albums. The **Song** entity contains information about songs, including their title, genre, and label. This has a one-to-many relationship with the Album entity as albums can contain multiple songs. The Song entity also has a one-to-many relationship with the StreamingData entity and Collaborations entity. The **StreamingData** entity contains information such as the strem revenue and platform while the **Collaborations** entity contains information such as the Collab ID and role. Songs generate revenue through multiple different streaming platforms and a single song can be available on multiple streaming services. Collaborations also shares a one-to-many relationship with Artist as artists can have many different collaborations with various artists. 

<p align="center"> ────୨ৎ────

Beyond recorded music, artists also earn revenue from live performances. The **Concert** entity contains information about artist's concerts, such as the concert date and tour name. This has a one-to-many relationship with Artist as artists can hold multiple concerts. The Concert entity also holds one-to-many relationships with the Venue entity and Ticket entity. The **Venue** entity contains information such as the venue name and city while the **Ticket** entity contains information such as the seat number and ticket price. Each concert takes place at a venue and a venue can hold multiple concerts while concerts can only be held at one venue at a time. Since each concert generates revenue through ticket sales, the Ticket entity shows that a concert can sell multiple tickets while a ticket can only be assigned to one concert at a time. 

<p align="center"> ────୨ৎ────

Overall, our database supports managing multiple record labels and their artists, tracking music releases and streaming performance, recording artist collaborations and contract details, monitoring concert events and ticket sales, calculating royalty distributions and revenue sources, and recognizing artists' achievements through various awards. It provides a comprehensive view of artist careers, music performance, and revenue tracking ensuring that the record labels under the conglomerate are able to make data-driven decisions to maximize profitability and artist success. 


# DATA DICTIONARY

### ARTIST TABLE
![ARTIST](https://github.com/user-attachments/assets/fcb66825-90ec-44f2-b01e-54da453cb93f)
### ALBUM TABLE
![ALBUM](https://github.com/user-attachments/assets/82f22448-a616-4727-8fa8-e596d6639e74)
### STREAMING DATA TABLE
![STREAMING DATA](https://github.com/user-attachments/assets/abc4302b-2ec3-467f-a88b-017173ca2c75)
### SONG TABLE
![SONG](https://github.com/user-attachments/assets/2cea2e21-d3ec-4992-8c9a-c2175b3aa294)
### AWARDS TABLE
![AWARDS](https://github.com/user-attachments/assets/c77345b6-51dd-48fb-a47a-891e01c0be71)
### COLLABORATIONS TABLE
![COLLABORATIONS](https://github.com/user-attachments/assets/7e4ed45a-f1e5-44f0-a392-9669ff86c3da)
### CONCERT TABLE
![CONCERT](https://github.com/user-attachments/assets/c287cc60-b1b1-4185-bb79-20255b297055)
### TICKET TABLE
![TICKET](https://github.com/user-attachments/assets/2557bc6d-e278-4215-a836-39e64241cea0)
### VENUE TABLE
![VENUE](https://github.com/user-attachments/assets/c152deb0-97e7-480e-865c-fdb96a803b26)
### ROYALTY TABLE
![ROYALTY](https://github.com/user-attachments/assets/5bcb78fe-2221-4e78-964e-a580c5f86b13)
### RECORD LABEL TABLE
![RECORDLABEL](https://github.com/user-attachments/assets/92f698a2-4f70-4eac-9e8d-ffaf8cee7f2d)
### CONTRACT TABLE
![CONTRACT](https://github.com/user-attachments/assets/9ebbe91e-9e12-4d26-8208-36fe9f0ee889)


# QUERIES
![DATABASE](https://github.com/user-attachments/assets/5b127818-bbb3-4851-9639-c726aeaca35d)

### QUERY 1
Find artists whose concert and streaming revenue combined exceeds $200,000. 
![QUERY 1](https://github.com/user-attachments/assets/8f909940-4f4f-44ba-b833-f1cb80afb224)
- For a record label executive or artist manager, understanding which artists generate the most revenue from both live performances and digital streaming is crucial for strategic decision-making. Managers can prioritize high-revenue artists for increased promotional budgets, exclusive collaborations, or extended concert tours. If an artist is exceeding revenue expectations, the label may extend contracts, negotiate higher revenue splits, or provide incentives for further projects. 

### QUERY 2
Find songs that have more streams than their album's average.
![QUERY 2](https://github.com/user-attachments/assets/b057c159-8a92-4049-b96f-a024ea82fca2)

- For record label executives, artist managers, and marketing teams, understanding which songs are outperforming their album's average streaming count is critical for strategic decision making and promotional planning. This query identifies standout tracks that are resonating with audiences more than other songs on the same album, allowing labels to focus their efforts on maximizing engagement and revenue from these tracks. If specific songs are outperforming their album averages, labels can increase marketing efforts to increase revenue.  

### QUERY 3
Find record labels that manage artists from at least 3 different genres.
![QUERY 3](https://github.com/user-attachments/assets/dffc9cbe-6546-4a3a-864d-1424129cb652)

- Understanding which labels diversify their artist rosters across multiple genres is crucial for strategic planning, risk management, and market positioning. This query helps identify record labels with broad genre representation, allowing for better decision making regarding things like investments, collaborations, and audience targeting. Labels managing artists across multiple genres can also tap into different fan bases, increasing overall exposure. 

### QUERY 4
Find the venues that have hosted the most concerts.
![QUERY 4](https://github.com/user-attachments/assets/a1a8ad08-3e7f-45bb-90d8-b6be66e32682)

- For record label executives, knowing which venues have hosted the most concerts is crucial for strategic tour planning, artist bookings, and revenue forecasting. Higher frequency venues indicate strong demand and reliability for hosting concerts and managers can prioritize these venues for future tour dates, ensuring maximum attendance. 

### QUERY 5
Find the total number of concerts and the average ticket price for each artist. 
![QUERY 5](https://github.com/user-attachments/assets/07eeca1b-9aa4-424a-b5fc-966af2a0bbf3)

- For record label executives, tour managers, and event coordinators, understanding the number of concerts an artist has performed and their average ticket price is essential for tour planning, revenue forecasting, and pricing strategy optimization. The total number of concerts an artist has performed is a strong indicator of fan engagement and touring success.
Artists with high concert numbers may have a dedicated live audience, suggesting strong ticket sales potential. The average ticket price per artist helps determine whether an artist is undervalued or overpriced in the market, meaning that if an artist’s ticket prices are too low compared to their demand, managers may increase pricing for future concerts. If prices are too high and concert attendance is low, adjustments can be made to improve affordability and accessibility.

### QUERY 6
List the top 3 most popular songs by stream count and their associated artist names. 
![QUERY 6](https://github.com/user-attachments/assets/ae0883b3-6b8d-4a5c-b081-a4213d1e4b24)

- For record label executives, streaming platform analysts, and artist managers, identifying the top three most streamed songs is critical for marketing strategies, revenue optimization, and future investment decisions. This query helps pinpoint which songs are performing exceptionally well, allowing managers to focus their promotional efforts on high-engagement tracks to maximize revenue and exposure. The top-performing songs indicate what is resonating most with listeners. Managers can increase marketing efforts for these songs through social media campaigns, influencer partnerships, and digital ads.


### QUERY 7
List which collaborations generate the highest streaming revenue across all platforms
![QUERY 7](https://github.com/user-attachments/assets/1125d8c6-ea20-4fcc-9f01-642232705259)

- For record label executives, A&R teams, streaming platform analysts, and artist managers, understanding which collaborations generate the highest streaming revenue is crucial for strategic decision-making in artist pairings, marketing investments, and contract negotiations. If a specific artist pairing consistently generates high streaming revenue, labels can prioritize similar collaborations in future projects. Managers can strategically match artists who have strong synergy and cross-audience appeal to maximize streaming potential. Analyzing collaboration success rates across genres can also guide artist development and talent scouting strategies.

### QUERY 8
Find artists with high streaming revenue and calculate how much of that revenue is owed to the record label based on the contract. 
![QUERY 8](https://github.com/user-attachments/assets/2e5c4466-82c2-458d-a308-d43c294ab1e4)

- For record label executives, finance teams, and artist managers, understanding how much revenue an artist generates from streaming and how much of that revenue belongs to the record label is essential for financial planning, contract enforcement, and profit optimization. By identifying artists with high streaming revenue, record labels can measure which artists are the most profitable. This allows executives to determine whether investments in marketing, production, and promotions are yielding strong returns. If an artist is exceeding streaming expectations, the label may consider renegotiating their contract to secure a more favorable revenue split. Conversely, if an artist is underperforming relative to their contract terms, the label may reconsider their investment strategy.

### QUERY 9
List artists with the total amount of songs they have only if they have more than the average amount of songs across all artists.
![QUERY 9](https://github.com/user-attachments/assets/ff98e3a5-d8e9-4d0a-9e26-2b7a66f419ce)

- For record label executives, A&R teams, and music streaming analysts, identifying artists with a higher-than-average number of songs is valuable for understanding productivity levels, content output strategies, and revenue potential. Artists who release more songs than the average are typically more active in the industry. Labels can prioritize these artists for long-term contracts and additional project funding. More songs also mean more opportunities for streaming income, as each track contributes to overall streaming numbers.

### QUERY 10
List the total revenue from ticket sales for each concert and only include concerts where the total revenue is greater than the average ticket price across all concerts. 
![QUERY 10](https://github.com/user-attachments/assets/93458cba-5455-42a6-810b-172e1b287833)

- For record label executives, tour managers, event coordinators, and financial analysts, identifying concerts that generate above-average revenue from ticket sales is crucial for strategic tour planning, pricing optimization, and financial forecasting. Concerts with above-average ticket revenue are strong indicators of high demand, effective pricing strategies, and successful marketing efforts. These concerts can be used as a model for future event planning. By comparing total ticket revenue to the average ticket price, managers can determine whether higher-priced tickets contribute to profitability. If higher ticket prices correlate with increased revenue, pricing models can be adjusted for future concerts and tours.



# DATABASE INFO
Database Name: ns_Sp25_21482_Group4

All queries can be accessed through stored procedures that can be called using
**CALL TP_Qx ();**\
Where x is to be replaced by the query number.





