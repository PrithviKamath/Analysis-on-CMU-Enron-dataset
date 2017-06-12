<img src="https://github.com/PrithviKamath/Analysis-on-CMU-Enron-dataset/blob/master/Extras/Enron_logo.jpg"></img>
<b>Enron Dataset</b>

<b>Summary:</b> <br />
• A Houston-based energy giant, Enron Corporation was one of the biggest companies in the world, dealing in everything from natural gas production to telecommunications <br />
• At Enron's peak, its shares were worth $90.75, but after the company declared bankruptcy on December 2, 2001, they plummeted to $0.67 by January 2002 <br />
• By the fall of 2000, Enron was starting to crumble under its own weight <br />
• CEO Jeffrey Skilling used mark-to-market accounting to hide the financial losses and make the company appear more profitable <br />
• Below are some of the analysis I have deduced from an CMU Enron dataset (https://www.cs.cmu.edu/~./enron/enron_mail_20150507.tgz) <br />

<b>Analysis 1:</b> Find the list of people who have sent and received maximum number of emails. <br />

<b>Approach:</b> <br />
• Extract 3 parts- email sent to, email received from and body of the email by traversing through all the subdirectories, subfolder and files <br />
• Append them in a list named to_email_list, from_email_list and email_body and neglect the none values as and when encountered <br />
• Replace the new line characters- ‘\n’, tab separated values- ‘\t’ and spaces with empty string- “” to overcome them <br />
• Find the frequency of each items in to_email-list and from_email_list and store it in to_sorted_names and from_sorted-names list <br />
• Save the output in to_email_list.csv, from_email_list.csv and email_body.csv respectively in an Output folder in the parent directory <br />

<b>Conclusion:</b> <br />
• Maximum number of emails have been sent to ‘richard.shapiro@enron.com’ <br />
Mr. Richard Shapiro was Enron’s top lobbyist who took part in an organized attempt to influence legislators through his wrong doing <br />

<b>Files:</b> Enron Analysis 1 <br />
<img src="https://github.com/PrithviKamath/Analysis-on-CMU-Enron-dataset/blob/master/Output/from_email_list.PNG"></img>
 <br />


<b>Analysis 2:</b> Analysing Mr. Kenneth Lay’s emails in his 'deleted_item' folder  <br />

<b>Approach:</b> <br />
• Extract the body of every mail deleted by Mr. Kenneth Lay by traversing through all the subdirectories, subfolders and files <br />
• Append them in a list named email_body <br />
• Parse through each item in the list and split each word using .split(‘ ’) <br />
• Find the frequency of these words and store them in a sorted_words list <br />
• From the list we understand that the word 'bankruptcy' has occured considerable number of times  <br />
• Hence we find the number of emails containing with word 'bankruptcy'  <br />
• We also calculate the total number of emails in the 'deleted_item' folder and compare the difference  <br />

<b>Conclusion:</b> <br />
• Words like ‘bankruptcy’, ‘millions’, ‘stock’ and ‘buy’ in the emails in the deleted_items folder suggests that Mr. Kenneth Lay tried to delete some mails which could suggest wrong doings <br />
• Words like ‘Enron’, ‘gas’, ‘energy’ and ‘communication’ suggest what kind of company Enron was. Enron Corporation was an American energy, commodities, and services company <br />
• We notice that bankruptcy is repeated just 2 times across 1121 files out of 1126 files in the deleted_items folder <br />
• On closer inspection we understand that body of these 1121 emails is the same with changes in salutations <br />
• Hence we can conclude that there might have been a survey or a poll conducted after the Enron scandle was publisized and the people who signed up for this survey have sent the same mail to My Kenneth Lay  <br />

<b>Files:</b> Enron Analysis 2  <br />
<img src="https://github.com/PrithviKamath/Analysis-on-CMU-Enron-dataset/blob/master/Output/Analysis_2.PNG"></img>
<img src="https://github.com/PrithviKamath/Analysis-on-CMU-Enron-dataset/blob/master/Output/Analysis_3.PNG"></img>
<br />

<b>Analysis 3:</b> Find who has sent and received the maximum number of emails on weekends.  <br />

<b>Approach:</b> <br />
• Iterate through all the emails and categorize them according to the datetime stamp  <br />
• List the top 10 people who hace sent and received maximum number of emails  <br />
• Save the entire result in an 'WeekendMails.csv' file  <br />
• For the topmost person in this list, take all his/her weekend emails (sent and received) and calculate save it in a bloblist  <br />
• Calculate Term Frequency- Inverse Document Frequency (TF-IDF) for every word in the body of these mails and add the top word to a word corpus  <br />
• Display this word corpus as a wordcloud  <br />

<b>Conclusion</b> <br />
• In the list of most people sending and receiving emails on weekends, there is a considerable amount of difference between the topmost person and the rest  <br />
• On further analysing these emails in a word cloud, we get the following term which are used often  <br />
     -1. Financial term like 'expense', 'rate', 'insurance', 'transaction', 'book' and 'market'  <br />
     -2. Locations like 'California', 'Madrid', 'Ontario', 'Korea', 'India', 'US', 'UK'  <br />
     -3. Person names like 'Elizabeth', 'Anderson', 'Clinton', 'Kaufman' and 'Billie'  <br />
     -4. Establishments like 'IBM', 'BlackBerry', 'MIT', 'ONGC' and 'Azurix'   <br />
• Words like 'Trap', 'Court', 'Withdrawal', 'Tax' and 'Traded' are also used quite often   <br />

<b>Files:</b> Enron Analysis 3 <br />
<img src="https://github.com/PrithviKamath/Analysis-on-CMU-Enron-dataset/blob/master/Output/wordcloud.PNG"></img> <br />
