# LSApp: Large dataset of Sequential mobile App usage

Recent years have witnessed a rapid growth in the use of mobile devices, enabling people to access the Internet in various contexts. More than 77% of Americans now own a smartphone, with an increasing trend in terms of the time people spend on their phones. More recently, with the release of intelligent assistants such as Google Assistant, Apple Siri, and Microsoft Cortana, people are experiencing mobile search through a single voice-based interface. These systems introduce several research challenges. Given that people spend most of their times in apps and, as a consequence, most of their search interactions would be with apps (rather than a browser), one limitation is that users are unable to use a intelligent assistants to search within many apps.

So far, all the studies on mobile information retrieval have focused on a single interface for search (i.e., Google, Bing, etc.). However, in our previous works [[1](#ref1), [2](#ref2)], we showed that this is no longer the case with the availability of various apps featuring their own search engine. Nowadays, users tend to search for various modalities of information using different apps. As of 2016, the average U.S. user spends 5 hours on mobile devices per day, with just 8% of it spent in the phone's browser. In fact, people spend most of their time (72%) using apps that have their own search feature. Moreover, according to [[1](#ref1)] users prefer to submit the majority of their queries to a more specific app (vs. Google or Bing).

LSApp is a complementary collection to [ISTAS](https://github.com/aliannejadi/istas) where we also collect sequential app usage events of the users. We recruited 292 participants through and asked them to install uSearch on their smartphones and let it run for at least 24 hours. During the study, we asked the participants to report their mobile searches using uSearch as soon as they did the search. In the meantime, we collected their app usage statistics with their consent. 

## uSearch 

In order to facilitate the query report procedure, we developed an Android app called [uSearch](https://github.com/aliannejadi/usearch). The user interface of uSearch consists of three sections. The upper part lists all the apps that are installed on the phone, with the most used apps ranked higher. The participants were supposed to select the app in which they had done their real-life search (e.g., Facebook). In the second section, the participants were supposed to enter exactly the same query that they had entered in the target app. Finally, the lower part of the app, provided them easy access to a unique ID of their device and an online survey on their demographics and backgrounds.

## Basic Statistics

During the study period, with the help of 292 participants, we were able to collect 599,635 app usage records. Here, we summarize the main characteristics of the participants based on the submitted surveys. 59% of the participants were female and 50% aged between 25 and 34. Participants were from all kinds of educational backgrounds ranging from high school diploma to PhD. In particular, 32% of them had a college degree, followed by 30% with a bachelor's degree. Smartphone was the main device used for connecting to the Internet for 53% of the participants, followed by laptop (25%). Among the participants, 67% used their smartphones more often for personal reasons rather than work. Finally, half of the participants stated that they use their smartphones 4 hours a day or more. More insights about LSApp is available in the table below, as well as our [ACM TOIS paper](#ref3) paper.

            # app usage records                   599,635
            # sessions                            76,247
            # unique apps                         87
            # users                               292
            Mean duration/user                    15 days
            Mean session time length              5:26 ± 9:29
            Median session time length            1:46
            Mean unique apps in each session      2.18 ± 1.46
            Median unique apps in each session    2
            Mean app switches within a session    5.46 ± 11.20
            Median app switches within a session  2
            # train instances                     464,903
            # validation instances                66,300
            # test instances                      132,751



## Format

Upon downloading the data, you get one compressed file. You can uncompress it using gzip, zip etc. The main file is a TSV file, called lsapp.tsv. Each row of LSApp consists of the following columns:

* user_id: the unique user identifier.
* session_id: the unique session identifier.
* timestamp: time when the app usage event is recorded.
* app_name: name of the app.
* event_type: type of the event recorded. Possible values: Opened, Closed, User Interaction, Broken 


Below are two example rows from the tasks file:

user\_id |	session\_id |	timestamp	| app\_name	| event\_type
-- | -- | -- | -- | --
0	| 1	| 2018-01-16 06:01:05 | 	Minesweeper Classic (Mines)	| Opened
0	| 1	| 2018-01-16 06:01:05	| Minesweeper Classic (Mines) |	Closed
0	| 2	| 2018-01-16 06:25:54	| Gmail	| User Interaction
0| 	2	| 2018-01-16 06:26:05	| Google	| Opened
0	| 2	| 2018-01-16 06:26:10	| Google	| Closed

## Citation

    @inproceedings{AliannejadiTOIS21,
        author    = {Aliannejadi, Mohammad and Zamani, Hamed and Crestani, Fabio and Croft, W. Bruce},
        title     = {Context-Aware Target Apps Selection and Recommendation for Enhancing Personal Mobile Assistants},
        booktitle = {{ACM} Transactions on Information Systems ({TOIS})},
        year      = 2021
      }

## Acknowledgments

This work was a joint effort by Università della Svizzera italiana (USI), Lugano, Switzerland and University of Massachusetts Amherst, Amherst, MA, USA. Thanks to Jacopo Fidacaro, Luca Costa, Mohammad Aliannejadi, Hamed Zamani, Fabio Crestani and W. Bruce Croft for their efforts in developing this dataset.

## References

<a name="ref1">[1]</a> Mohammad Aliannejadi, Hamed Zamani, Fabio Crestani, and W. Bruce Croft. 2018. Target Apps Selection: Towards a Unified Search Framework for Mobile Devices. In Proceedings of the 41st International ACM SIGIR Conference on Research and Development in Information Retrieval, pages 215-224

<a name="ref2">[2]</a> Mohammad Aliannejadi, Hamed Zamani, Fabio Crestani, and W. Bruce Croft. 2018. In Situ and Context-Aware Target Apps Selection for Unified Mobile Search. In Proceedings of the 27th ACM International Conference on Information and Knowledge Management, pages 1383-1392

<a name="ref3">[3]</a> Mohammad Aliannejadi, Hamed Zamani, Fabio Crestani, and W. Bruce Croft. 2020. Context-Aware Target Apps Selection and Recommendation
for Enhancing Personal Mobile Assistants. ACM Transactions on Information Systems (TOIS).
