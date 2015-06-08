Rajat Bhageria NETS 150 HW 3
March 26, 2015

Overall: I used Jsoup to complete this assignment. In this readMe.txt file, I have detailed all the questions, all my answers, and the algorithms I used--in quite a lot of detail--to solve the problems. In terms of URL, I only hard-coded the main URL of the portal and then use relative links and hrefs to navigate to the various webpages. The answers to the theoretical part of my assignment is attached in a PDF. I additionally completed 1 extra credit assignment. 

Program Structure: I have created two classes. I have created a "Questions" class in which each question (or extra credit question) is a separate method (with appropriate documentation and arguments). The Main class is called "Main," and in this class I create a instance of the Questions object; I then call all the methods for the questions in the main class and do all the printing there.  In the Main class, you can chang the instance variables that are then passed into the methods in Question to change the parameters (and thus represent the italicized words in the questions).

Please do note that some of the questions take some time to process; if it is taking a long time, it is probably still processing. 

Part 1: See attached PDF document

Part 2: Programming

Question 1: List all movies nominated for the Best Picture award for which one of the Production Companies was Disney.

	Answer: 
		Mary Poppins
		Beauty and the Beas
		Up
		Toy Story 3

	How I found the answer: I first went to the page for best picture in the Academy Awards. Then I used the getElementByTag() method to select all elements with the tag "td" (each individual movie). I then applied the .text() method on each "td," and if it returned "Disney," I used the previousElementSibling() method on the "td" to find the name of the movie (this is because I knew that the title "td" was a previous sibling of the producer "td" in any particular "tr"). I then added the name of the movie to an ArrayList, and continued transversing through the "tds." 


Question 2: For the Best Original Screenplay award, list the writers for the movie that was nominated/won titled Divorce, Italian Style

	Answer: 
		Ennio de Concini
		Pietro Germi
		Alfredo Giannetti

	How I found the answer: I first created a list of all the "td" on the page. I then found the "td" with the text tag of the movie I'm searching for (in this case, "Divorce, Italian Style"). After finding the correct td for the movie I'm looking for, I use nextElementsSibling() method to the block of HTML that contains "a" tags for all the writers; I then use getElementByTag() method to select each individual "a" tag block, and then use .text() method to find the writer  in the block and add it to an ArrayList, which I then return. 

Question 3: List all actors nominated for a Best Leading Actor award whose role was playing a King:

	Answer: 
		Charles Laughton
		Laurence Olivier
		Yul Brynner
		Laurence Olivier
		Peter O'Toole
		Peter O'Toole
		Richard Burton
		Kenneth Branagh
		Nigel Hawthorne
		Colin Firth

	How I found the answer: Initially, I found all the elements with the tag "td." I then added a conditional statement where if the text of the td method started with "King," then I added the actor associated with that King role to an arrayList (using a series of two previousElementSibling() method calls). I lastly returned the arrayList. 


Question 4: For the year 2006, list all actresses nominated for a Best Leading Actress award along with the
movie and their age that year.

	Answer: 
		Actress: Helen Mirren
		Film: The Queen
		Age: 61
		Actress: Penélope Cruz
		Film: Volver
		Age: 32
		Actress: Judi Dench
		Film: Notes on a Scandal
		Age: 72
		Actress: Meryl Streep
		Film: The Devil Wears Prada
		Age: 57
		Actress: Kate Winslet
		Film: Little Children
		Age: 31

	How I found the answer: Initially, I conencted to the correct URL using Jsoup and the getLink() method. Now, I used an enhanced for loop to find all elements that have the "tr" tag. Since I want data for only a specific data, I figure out the next year, and then ensure that all the trs I'm considering occur between the tr for the year entered and 1 + the year entered for the user; this ensures that I only receive the data for the correct years. Now I transverse the data (using .child() and .nextelementSibling() methods) to retrive the name of the actress, the name of the film she acted in, and an href of her own Wikipedia page. I then use this href using Jsoup to create a new document that I will now use to find the date on which she was born. More specifically, I use the getElementsByClass("bday") method because I know that the only element that has her birthday has the "bday" class. I then use Integer.parseInt and simple subtraction to find the age of the actress on that year's award ceremony. Finally, I add all the necessary data to an ArrayList and return it. 


Question 5: List all directors (with the corresponding movies) that have been nominated for at least 4 Best Director awards.

	Answer: 
		John Ford
		Number of Awards: 5
		Movies: 
		The Quiet Man
		How Green Was My Valley
		The Grapes of Wrath
		Stagecoach
		The Informer


		William Wyler
		Number of Awards: 12
		Movies: 
		The Collector
		Ben-Hur
		Friendly Persuasion
		Roman Holiday
		Detective Story
		The Heiress
		The Best Years of Our Lives
		Mrs. Miniver
		The Little Foxes
		The Letter
		Wuthering Heights
		Dodsworth


		Frank Capra
		Number of Awards: 6
		Movies: 
		It's a Wonderful Life
		Mr. Smith Goes to Washington
		You Can't Take It With You
		Mr. Deeds Goes to Town
		It Happened One Night
		Lady for a Day


		Billy Wilder
		Number of Awards: 8
		Movies: 
		The Apartment
		Some Like It Hot
		Witness for the Prosecution
		Sabrina
		Stalag 17
		Sunset Boulevard
		The Lost Weekend
		Double Indemnity


		David Lean
		Number of Awards: 7
		Movies: 
		A Passage to India
		Doctor Zhivago
		Lawrence of Arabia
		The Bridge on the River Kwai
		Summertime
		Great Expectations
		Brief Encounter


		Steven Spielberg
		Number of Awards: 7
		Movies: 
		Lincoln
		Munich
		Saving Private Ryan
		Schindler's List
		E.T. the Extra-Terrestrial
		Raiders of the Lost Ark
		Close Encounters of the Third Kind


		Fred Zinnemann
		Number of Awards: 7
		Movies: 
		Julia
		A Man for All Seasons
		The Sundowners
		The Nun's Story
		From Here to Eternity
		High Noon
		The Search


		Elia Kazan
		Number of Awards: 5
		Movies: 
		America, America
		East of Eden
		On the Waterfront
		A Streetcar Named Desire
		Gentleman's Agreement


		George Stevens
		Number of Awards: 5
		Movies: 
		The Diary of Anne Frank
		Giant
		Shane
		A Place in the Sun
		The More the Merrier


		Clint Eastwood
		Number of Awards: 4
		Movies: 
		Letters from Iwo Jima
		Million Dollar Baby
		Mystic River
		Unforgiven


		Frank Lloyd
		Number of Awards: 4
		Movies: 
		Mutiny on the Bounty
		Cavalcade
		Drag
		The Divine Lady


		Joseph L. Mankiewicz
		Number of Awards: 4
		Movies: 
		Sleuth
		5 Fingers
		All About Eve
		A Letter to Three Wives


		Martin Scorsese
		Number of Awards: 8
		Movies: 
		The Wolf of Wall Street
		Hugo
		The Departed
		The Aviator
		Gangs of New York
		Goodfellas
		The Last Temptation of Christ
		Raging Bull


		Woody Allen
		Number of Awards: 7
		Movies: 
		Midnight in Paris
		Bullets over Broadway
		Crimes and Misdemeanors
		Hannah and Her Sisters
		Broadway Danny Rose
		Interiors
		Annie Hall


		George Cukor
		Number of Awards: 5
		Movies: 
		My Fair Lady
		Born Yesterday
		A Double Life
		The Philadelphia Story
		Little Women


		Michael Curtiz
		Number of Awards: 5
		Movies: 
		Casablanca
		Yankee Doodle Dandy
		Four Daughters
		Angels with Dirty Faces
		Captain Blood


		John Huston
		Number of Awards: 5
		Movies: 
		Prizzi's Honor
		Moulin Rouge
		The African Queen
		The Asphalt Jungle
		The Treasure of the Sierra Madre


		Francis Ford Coppola
		Number of Awards: 4
		Movies: 
		The Godfather Part III
		Apocalypse Now
		The Godfather Part II
		The Godfather


		Mike Nichols
		Number of Awards: 4
		Movies: 
		Working Girl
		Silkwood
		The Graduate
		Who's Afraid of Virginia Woolf?


		Robert Altman
		Number of Awards: 5
		Movies: 
		Gosford Park
		Short Cuts
		The Player
		Nashville
		MASH


		Clarence Brown
		Number of Awards: 5
		Movies: 
		The Yearling
		National Velvet
		The Human Comedy
		A Free Soul
		Anna Christie


		Alfred Hitchcock
		Number of Awards: 5
		Movies: 
		Psycho
		Rear Window
		Spellbound
		Lifeboat
		Rebecca


		King Vidor
		Number of Awards: 5
		Movies: 
		War and Peace
		The Citadel
		The Champ
		Hallelujah
		The Crowd


		Federico Fellini
		Number of Awards: 4
		Movies: 
		Amarcord
		Satyricon
		8½
		La Dolce Vita


		Stanley Kubrick
		Number of Awards: 4
		Movies: 
		Barry Lyndon
		A Clockwork Orange
		Gillo Pontecorvo
		Dr. Strangelove


		Sidney Lumet
		Number of Awards: 4
		Movies: 
		The Verdict
		Network
		Dog Day Afternoon
		12 Angry Men


		Peter Weir
		Number of Awards: 4
		Movies: 
		Master and Commander: The Far Side of the World
		The Truman Show
		Dead Poets Society
		Witness

	How I found the answer: Initially, on the page with all the awards for best director, I found all the elements with the li tag. At this point, I wanted to determine which directors were nominated for more than x awards. To make sure I was selecting the right lis, I noticed that each of the lis I wanted contained a "-" and ended with an ")"; I was then able to find the correct lis; I then used substrings to find the number of times the particular actor has been nominated, used the .attr("title") method to find their name, and used the .attr("href") method to find the link to that specific director's page. I now created a new document using Jsoup connect and that url; 


Question 6: List the country (with the corresponding movies) that has been nominated the most number of times for Best Foreign Language Film award.

	Answer: 
		Country: France

		Movies:
		The Class
		Au Revoir Les Enfants (Goodbye, Children)
		My Uncle
		The Last Metro
		Camille Claudel
		Get Out Your Handkerchiefs
		A Simple Story
		A Prophet
		The Discreet Charm of the Bourgeoisie
		Monsieur Vincent
		Gervaise
		Cousin, Cousine
		East-West
		A Man and a Woman
		The Umbrellas of Cherbourg
		Live for Life
		Indochine
		Stolen Kisses
		Forbidden Games 
		My Night with Maud 
		Entre Nous
		Amélie
		La Vérité
		The Taste of Others
		Ridicule
		Black Orpheus
		Madame Rosa
		Hoa-Binh
		Joyeux Noël
		Coup de Torchon ('Clean Slate')
		Lacombe, Lucien
		Cyrano de Bergerac
		The Chorus
		Three Men and a Cradle
		Gates of Paris
		Day for Night
		Sundays and Cybele
		Betty Blue

	How I found the answer: First I directed to the Best Foreign Film Page. Then, I found found all the elements with the "tr" tag in them; I then made my way to the main table section of the page (to do this I knew filtered all the trs by the ones that began with "19" or "20" knowing that the first column in each row was a year). I then found the name of each movie (the second child from the year column) and the name of the country where the movie is from (the 4th child from the year column). After this, I had to sort all the movies by the country they were from; to do this, I created a HashSet with the keys being the string names of the country, and the values being a HashSet of the movies associated with that country. I then iterated through all the countries and asked if the particular country was already in the hashset; if it was, I added the corresponding movie (fron that row) to the HashSet for that country; if it wasn't, I created a new key (the country name) and created a new HashSet with the movie name. Now I had to sort the HashMap and find out which HashSet had the largest size (and hence find the country with the most nominations); I did this by iterating through the map with a simple enhanced for loop and keySets; every time I found a HashSet with a size bigger than the previously largest HashSet, I transferred the contents of the new HashSet to an ArrayList and then returned it. 


Question 7: List all movies nominated for the Best Animated Feature award that starred Tom Hanks:

	Answer: 
		Toy Story 3

	How I found the answer: Initially, I connected to the correct wikipedia page for the type of award. Then, I found all the elements with the "tr" tag and then selected all the elements witha an "a" tag within; after removing "a" tags that are not part of thef central table I am considering, I find the link to the page of each movie that has been nominated for the best animated feature. Individually, I connect to each of these pages, and then I find all the tr elements that start with "Starring." I then check each tr element (the actors that star in the film) and see if the String contains the actor in question (originally Tom Hanks); if a particular film that hsas been nominated for the award also has the particular actor as a star, I add the movie to an HashSet (to prevent repeats) and then return the Set. Note that the vast majority of the award pages had completely different structures than the Best Animated Feature, and so this algorithm only works with a small subset of the awards (that have the same format as the Best Animated Feature page).


Question 8: Wildcard: List the budgets (and the names) of each of the films that were nominated for Best Director award (in chronological order):

	Answer: 
		7th Heaven (1927 film) 
		Budget $1.3 million


		The Divine Lady 
		Budget Stoklot I


		The Patriot (1928 film) 
		Budget $1 million


		All Quiet on the Western Front (1930 film) 
		Budget $1.2 million


		A Free Soul 
		Budget $529,000


		Cimarron (1931 film) 
		Budget $1,433,000


		Cavalcade (1933 film) 
		Budget $1,180,280


		Lady for a Day 
		Budget $300,000


		Little Women (1933 film) 
		Budget $424,000


		It Happened One Night 
		Budget $325,000


		The Thin Man (film) 
		Budget $226,408


		The Informer (1935 film) 
		Budget $243,000


		Mutiny on the Bounty (1935 film) 
		Budget $1,950,000


		Captain Blood (1935 film) 
		Budget $1,000,000 (estimated)


		Mr. Deeds Goes to Town 
		Budget $845,710


		My Man Godfrey 
		Budget $656,000 (est.)


		The Great Ziegfeld 
		Budget $2.183 million


		San Francisco (1936 film) 
		Budget $1,300,000


		The Good Earth (film) 
		Budget $2,816,000


		Stage Door 
		Budget $952,000


		A Star Is Born (1937 film) 
		Budget $1,159,000


		You Can't Take It With You (film) 
		Budget US$1,644,736 (est.)


		Boys Town (film) 
		Budget $772,000


		Boys Town (film) 
		Budget $862,000


		The Citadel (film) 
		Budget $1,012,000


		Gone with the Wind (film) 
		Budget $3.85 million


		Mr. Smith Goes to Washington 
		Budget $1.5 million


		Stagecoach (1939 film) 
		Budget $531,374


		Goodbye, Mr. Chips (1939 film) 
		Budget $1,051,000


		The Grapes of Wrath (film) 
		Budget $800,000


		The Philadelphia Story (film) 
		Budget $914,000


		Rebecca (1940 film) 
		Budget $1,288,000


		Kitty Foyle (film) 
		Budget $738,000


		How Green Was My Valley (film) 
		Budget $800,000


		Sergeant York (film) 
		Budget $1.4 million


		Citizen Kane 
		Budget $839,727


		Mrs. Miniver (film) 
		Budget $1.34 million


		Random Harvest (film) 
		Budget $1,210,000


		Kings Row 
		Budget $1,081,698


		Casablanca (film) 
		Budget $878,000


		The Human Comedy (film) 
		Budget $1.0 million


		The Song of Bernadette (film) 
		Budget $1.6 million


		Heaven Can Wait (1943 film) 
		Budget $1,115,000


		The More the Merrier 
		Budget $878,000


		Lifeboat (film) 
		Budget $1.59 million


		Wilson (film) 
		Budget $2,995,000


		Laura (1944 film) 
		Budget $1.02 million


		Double Indemnity (film) 
		Budget $980,000


		The Lost Weekend (film) 
		Budget $1.25 million


		National Velvet (film) 
		Budget $2,770,000


		Spellbound (1945 film) 
		Budget US$1.5 million


		The Best Years of Our Lives 
		Budget $2.1 million


		The Yearling (film) 
		Budget $3,883,000


		It's a Wonderful Life 
		Budget $3.18 million


		Gentleman's Agreement 
		Budget $1,985,000


		Crossfire (film) 
		Budget $678,000


		The Treasure of the Sierra Madre (film) 
		Budget $3 million


		Hamlet (1948 film) 
		Budget £527,530


		Battleground (film) 
		Budget $1,631,000


		The Heiress 
		Budget $2.6 million


		All About Eve 
		Budget $1.4 million


		The Asphalt Jungle 
		Budget $1,232,000


		Sunset Boulevard (film) 
		Budget $1.75 million


		A Place in the Sun (film) 
		Budget $2,295,304


		The African Queen (film) 
		Budget $1 million


		A Streetcar Named Desire (1951 film) 
		Budget $1.8 million


		An American in Paris (film) 
		Budget $2,724,000


		The Quiet Man 
		Budget $1.75 million


		Moulin Rouge (1952 film) 
		Budget USD$1.5 million (approx. £967,785)


		High Noon 
		Budget $730,000


		From Here to Eternity 
		Budget $1,650,000


		Shane (film) 
		Budget $3.1 million


		Lili 
		Budget $1,353,000


		Stalag 17 
		Budget $1,661,530


		Roman Holiday 
		Budget $1.5 million


		On the Waterfront 
		Budget $910,000


		Rear Window 
		Budget $1 million


		The High and the Mighty (film) 
		Budget $1.47 million


		Sabrina (1954 film) 
		Budget $2,238,813


		Marty (film) 
		Budget $350,000


		Bad Day at Black Rock 
		Budget $1,271,000


		Giant (1956 film) 
		Budget $5.4 million


		Around the World in 80 Days (1956 film) 
		Budget $6 million


		The King and I (1956 film) 
		Budget $4.55 million


		War and Peace (1956 film) 
		Budget $6 million


		Friendly Persuasion (film) 
		Budget $3 million


		The Bridge on the River Kwai 
		Budget $2,840,000.


		12 Angry Men (1957 film) 
		Budget $340,000


		Peyton Place (film) 
		Budget $2.2 million


		Witness for the Prosecution (1957 film) 
		Budget $3 million


		Gigi (1958 film) 
		Budget $3,319,355


		Cat on a Hot Tin Roof (1958 film) 
		Budget $2,345,000


		The Defiant Ones 
		Budget $778,000


		The Inn of the Sixth Happiness 
		Budget $3,570,000


		I Want to Live! 
		Budget $1,383,578


		Ben-Hur (1959 film) 
		Budget $15.2 million


		Room at the Top (1959 film) 
		Budget £280,000


		The Diary of Anne Frank (1959 film) 
		Budget $3.8 million


		Some Like It Hot 
		Budget $2,883,848


		The Nun's Story (film) 
		Budget $3.5 million


		The Apartment 
		Budget $3 million


		Sons and Lovers (1960 film) 
		Budget $805,000


		Never on Sunday 
		Budget $150,000


		Psycho (1960 film) 
		Budget $806,947


		West Side Story (film) 
		Budget $6 million


		Judgment at Nuremberg 
		Budget $3 million


		The Hustler (film) 
		Budget $2,125,000


		The Guns of Navarone (film) 
		Budget $6 million


		Lawrence of Arabia (film) 
		Budget $15 million


		To Kill a Mockingbird (film) 
		Budget $2 million


		The Miracle Worker (1962 film) 
		Budget $500,000


		David and Lisa 
		Budget $183,000


		Tom Jones (1963 film) 
		Budget $1 million or £467,000


		Hud (film) 
		Budget $2.35 million


		My Fair Lady (film) 
		Budget $17 million


		Zorba the Greek (film) 
		Budget $783,000


		Becket (1964 film) 
		Budget $3 million


		Dr. Strangelove 
		Budget $1.8 million


		The Sound of Music (film) 
		Budget $8.2 million


		Doctor Zhivago (film) 
		Budget $11 million


		Darling (1965 film) 
		Budget £400,000 (estimated)


		The Woman in the Dunes 
		Budget $100,000


		A Man for All Seasons (1966 film) 
		Budget $2 million


		Blowup 
		Budget $1.8 million


		Who's Afraid of Virginia Woolf? (film) 
		Budget $7,500,000


		The Graduate 
		Budget $3 million


		In Cold Blood (film) 
		Budget $3.5 million


		In the Heat of the Night (film) 
		Budget $2 million


		Guess Who's Coming to Dinner 
		Budget $4 million


		Bonnie and Clyde (film) 
		Budget $2.5 million


		Oliver! (film) 
		Budget $10 million


		The Lion in Winter (1968 film) 
		Budget $10 million


		The Battle of Algiers 
		Budget $800,000


		Romeo and Juliet (1968 film) 
		Budget $850,000


		Midnight Cowboy 
		Budget $3.2 million


		Butch Cassidy and the Sundance Kid 
		Budget $6 million


		They Shoot Horses, Don't They? (film) 
		Budget $4.86 million


		Patton (film) 
		Budget $12,625,000


		MASH (film) 
		Budget $3,025,000


		Satyricon (1969 film) 
		Budget US$3 million


		Love Story (1970 film) 
		Budget $2.2 million


		Women in Love (film) 
		Budget $1.6 million


		The French Connection (film) 
		Budget $1.8 million


		The Last Picture Show 
		Budget $1.3 million


		Fiddler on the Roof (film) 
		Budget $9 million


		A Clockwork Orange (film) 
		Budget $2.2 million


		Cabaret (1972 film) 
		Budget $2,285,000


		Deliverance 
		Budget $2 million


		The Godfather 
		Budget $6–7 million


		Sleuth (1972 film) 
		Budget $3.5 million


		The Emigrants (film) 
		Budget $1,600,000


		The Sting 
		Budget $5.5 million


		Cries and Whispers 
		Budget $400,000


		Last Tango in Paris 
		Budget $1.25 million


		The Exorcist (film) 
		Budget $12 million


		American Graffiti 
		Budget $777,000


		The Godfather Part II 
		Budget $13 million


		One Flew Over the Cuckoo's Nest (film) 
		Budget $3 million


		Nashville (film) 
		Budget $2.2 million


		Barry Lyndon 
		Budget $11 million


		Dog Day Afternoon 
		Budget $1.8 million


		Rocky 
		Budget $1.075 million


		Network (film) 
		Budget $3.8 million


		All the President's Men (film) 
		Budget $8.5 million


		Annie Hall 
		Budget $4 million


		Star Wars (film) 
		Budget $11 million


		Close Encounters of the Third Kind 
		Budget $18 million


		Julia (1977 film) 
		Budget $7.84 million


		The Deer Hunter 
		Budget $15 million


		Interiors 
		Budget $10 million


		Coming Home (1978 film) 
		Budget $3 million


		Heaven Can Wait (1978 film) 
		Budget $15 million


		Midnight Express (film) 
		Budget $2.3 million


		Kramer vs. Kramer 
		Budget $8 million


		Apocalypse Now 
		Budget $31–31.5 million


		All That Jazz (film) 
		Budget $12 million


		La Cage aux Folles (film) 
		Budget FRF 7,000,000 ($1.4 million USD)


		Breaking Away 
		Budget $2.3 million


		Ordinary People 
		Budget $6 million


		The Elephant Man (film) 
		Budget $5 million


		Tess (film) 
		Budget $12 million (est.)


		The Stunt Man 
		Budget $3,500,000


		Raging Bull 
		Budget $18 million


		Reds (film) 
		Budget $32 million


		Chariots of Fire 
		Budget £3 million


		Atlantic City (1980 film) 
		Budget $7.2 million


		On Golden Pond (1981 film) 
		Budget $15 million


		Raiders of the Lost Ark 
		Budget $18 million


		Gandhi (film) 
		Budget $22 million


		The Verdict 
		Budget $16 million


		Das Boot 
		Budget 32 million DM ($12 million) (€24.3 million, 2009)


		Tootsie 
		Budget $21 million


		E.T. the Extra-Terrestrial 
		Budget $10.5 million


		Terms of Endearment 
		Budget $8 million


		Tender Mercies 
		Budget $4.5 million


		Silkwood 
		Budget $10 million


		Amadeus (film) 
		Budget $18 million


		Broadway Danny Rose 
		Budget $8 million


		Places in the Heart 
		Budget $9.5 million


		The Killing Fields (film) 
		Budget $14.4 million


		A Passage to India (film) 
		Budget £17 million


		Out of Africa (film) 
		Budget $28 million


		Prizzi's Honor 
		Budget $16 million


		Ran (film) 
		Budget $11,500,000


		Witness (1985 film) 
		Budget $12 million


		Platoon (film) 
		Budget $6 million


		Hannah and Her Sisters 
		Budget $6,400,000 (est.)


		A Room with a View (1985 film) 
		Budget £2.3 million


		The Mission (1986 film) 
		Budget £16,498,000


		Blue Velvet (film) 
		Budget $6 million


		The Last Emperor 
		Budget $23.8 million


		Hope and Glory (film) 
		Budget $9.3 million


		Moonstruck 
		Budget $15 million


		Fatal Attraction 
		Budget $14 million


		Rain Man 
		Budget $25 million


		A Fish Called Wanda 
		Budget $7,500,000


		Working Girl 
		Budget $28.6 million


		The Last Temptation of Christ (film) 
		Budget $7 million


		Born on the Fourth of July (film) 
		Budget $14 million


		Crimes and Misdemeanors 
		Budget $19 million


		Henry V (1989 film) 
		Budget $9 million


		My Left Foot 
		Budget £600,000


		Dead Poets Society 
		Budget $16.4 million


		Dances with Wolves 
		Budget $22 million


		The Godfather Part III 
		Budget $54 million


		Goodfellas 
		Budget $25 million


		The Silence of the Lambs (film) 
		Budget $19 million


		Bugsy 
		Budget $30 million


		Thelma & Louise 
		Budget $16.5 million


		Boyz n the Hood 
		Budget $6.5 million


		JFK (film) 
		Budget $40 million


		Unforgiven 
		Budget $14.4 million


		The Player (film) 
		Budget $8 million


		Scent of a Woman (1992 film) 
		Budget $31 million


		Howards End (film) 
		Budget $8 million


		The Crying Game 
		Budget £2.3 million ($3.6 million)


		Schindler's List 
		Budget $22 million


		The Piano 
		Budget $7 million


		The Remains of the Day (film) 
		Budget $15 million


		In the Name of the Father (film) 
		Budget $13 million


		Forrest Gump 
		Budget $55 million


		Bullets over Broadway 
		Budget $20 million


		Quiz Show (film) 
		Budget $31 million


		Pulp Fiction 
		Budget $8–8.5 million


		Braveheart 
		Budget $72 million


		Leaving Las Vegas 
		Budget $3.6 million


		Babe (film) 
		Budget $30 million


		Il Postino: The Postman 
		Budget $3 million


		Dead Man Walking (film) 
		Budget $11 million


		The English Patient (film) 
		Budget $27 million


		Fargo (film) 
		Budget $7 million


		The People vs. Larry Flynt 
		Budget $35 million


		Shine (film) 
		Budget $6 million


		Secrets & Lies (film) 
		Budget $4.5 million


		Titanic (1997 film) 
		Budget $200 million


		The Full Monty 
		Budget £3 million


		The Sweet Hereafter (film) 
		Budget $5,000,000


		L.A. Confidential (film) 
		Budget $35 million


		Good Will Hunting 
		Budget $10 million


		Saving Private Ryan 
		Budget $70 million


		Life Is Beautiful 
		Budget $20 million


		Shakespeare in Love 
		Budget $25 million


		The Thin Red Line (1998 film) 
		Budget $52 million


		The Truman Show 
		Budget $60 million


		American Beauty (1999 film) 
		Budget $15 million


		The Cider House Rules (film) 
		Budget $24 million


		Being John Malkovich 
		Budget $13 million


		The Insider (film) 
		Budget $90 million


		The Sixth Sense 
		Budget $40 million


		Traffic (2000 film) 
		Budget $46 million


		Billy Elliot 
		Budget £3 million ($5 million)


		Crouching Tiger, Hidden Dragon 
		Budget $17 million


		Gladiator (2000 film) 
		Budget $103 million


		Erin Brockovich (film) 
		Budget $51 million


		A Beautiful Mind (film) 
		Budget $58 million


		Gosford Park 
		Budget $19.8 million


		The Lord of the Rings: The Fellowship of the Ring 
		Budget $93 million


		Mulholland Drive (film) 
		Budget $15 million


		Black Hawk Down (film) 
		Budget $92 million


		The Pianist (2002 film) 
		Budget $35 million


		The Hours (film) 
		Budget $25 million


		Chicago (2002 film) 
		Budget $45 million


		Gangs of New York 
		Budget $97 - $100 million


		The Lord of the Rings: The Return of the King 
		Budget $94 million


		Lost in Translation (film) 
		Budget $4 million


		Mystic River (film) 
		Budget $30 million


		City of God (2002 film) 
		Budget $3.3 million


		Master and Commander: The Far Side of the World 
		Budget $150 million


		Million Dollar Baby 
		Budget $30 million


		Ray (film) 
		Budget $40 million


		Vera Drake 
		Budget $11 million


		Sideways 
		Budget $16 million


		The Aviator (2004 film) 
		Budget $110 million


		Brokeback Mountain 
		Budget $14 million


		Good Night, and Good Luck 
		Budget $7 million


		Crash (2004 film) 
		Budget $6.5 million


		Capote (film) 
		Budget $7 million


		Munich (film) 
		Budget $70 million


		The Departed 
		Budget $90 million


		Letters from Iwo Jima 
		Budget $19 million


		The Queen (film) 
		Budget £9.8 million ($15 million)


		Babel (film) 
		Budget $25 million


		United 93 (film) 
		Budget $15 million


		No Country for Old Men (film) 
		Budget $25 million


		There Will Be Blood 
		Budget $25 million


		Michael Clayton (film) 
		Budget $25 million


		Juno (film) 
		Budget $6.5


		The Diving Bell and the Butterfly (film) 
		Budget $14 million


		Slumdog Millionaire 
		Budget $15 million


		The Reader (2008 film) 
		Budget $32 million


		The Curious Case of Benjamin Button (film) 
		Budget $150 million


		Frost/Nixon (film) 
		Budget $25 million


		Milk (film) 
		Budget $20 million


		The Hurt Locker 
		Budget $15 million


		Avatar (2009 film) 
		Budget $237 million


		Precious (film) 
		Budget $10 million


		Up in the Air (2009 film) 
		Budget $25 million


		Inglourious Basterds 
		Budget $75 million


		The King's Speech 
		Budget £8 million ($15 million)


		Black Swan (film) 
		Budget $13 million


		True Grit (2010 film) 
		Budget $38 million


		The Social Network 
		Budget $40 million


		The Fighter 
		Budget $25 million


		The Artist (film) 
		Budget $15 million


		Midnight in Paris 
		Budget $17 million


		The Tree of Life (film) 
		Budget $32 million


		The Descendants 
		Budget $20 million


		Hugo (film) 
		Budget $150-170 million


		Life of Pi (film) 
		Budget US$120 million


		Amour (2012 film) 
		Budget $8.9 million


		Silver Linings Playbook 
		Budget $21 million


		Lincoln (2012 film) 
		Budget $65 million


		Beasts of the Southern Wild 
		Budget $1.8 million


		Gravity (film) 
		Budget $100 million


		12 Years a Slave (film) 
		Budget $22 million


		Nebraska (film) 
		Budget $12 million


		American Hustle 
		Budget $40 million


		The Wolf of Wall Street (2013 film) 
		Budget $100 million


		Birdman (film) 
		Budget $16.5 million


		The Grand Budapest Hotel 
		Budget €23 million


		Boyhood (film) 
		Budget $4 million


		Foxcatcher 
		Budget $24 million


		The Imitation Game 
		Budget $14 million

	How I found the answer: To find this answer, I initally connected to the Best Director page using Jsoup. Then, I fond all the elements that were tr tags; To make sure that I was getting elements from the main central table in the page, I noticed that they all contained "-," and so filtered with this parameter. I then found all the hrefs of each director and each movie that the director directed. Then, I used an enhanced for loop to transverse the array of directors and movies I had created. In this problem, I didn't care about the directors, and only the movie titles so the director name was excess. To take care of this and find the budget, I noticed that no director page contained a tr tag with the text of "Budget," but each movie page did. Therefore, I found the budget of each movie using the .startsWith("Budget") method for the text of each tr in the new document of the movie. I then added the title of the movie and the budget to an ArrayList and then returned it. 



Part 2 Extra Credit: Wildcard: The Average age of all the actors nominated for the Best Leading Actor in the year 1936 (variable) is: 

	Answer: 41 Years

	How I found the answer: After connecting to the correct Best Actor page using Jsoup and my getLink() method, I found all the elements in the document that start with "tr." Since the year I'm working with is an argument into the method, I figured out what the year right after the entered year is, and then transversed to the correct row in the central table of the page. I then tried to find the url to page of the actor who was nominated, and then used Jsoup to make another document with this second href. At this point, I used the getElementByClass("bday") method, and then used substrings and Integer.parseInt() to find an integer of the year that the particular actor was born. Using simple subtraction I was able to find the age of the actor when the actor was at the ceremony.I did this same process for all the actors that were nominated for best actor in the year passed in, and added these values to an ArrayList. Finally, I found averaged all the ages in the ArrayList and then returned the integer value of teh average age of the actors noiminated for best actor within a specific year. 