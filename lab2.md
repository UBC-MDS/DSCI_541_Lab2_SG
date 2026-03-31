# 541 Lab 2 - Privacy

## Required readings

We covered some of these videos during lecture, but I'm including them here so that you have everything in one place. There might be questions on specifics from the required readings whereas the optional readings are more of a general help, optional questions, and if you are interested to explore further.

- **Lec 3** Madhumita Murgia ["How data brokers sold my identity"](https://www.youtube.com/watch?v=AU66C6HePfg) (0:00 - 9:40)
- **Lec 3** Michal Kosinski ["Part One: The End of Privacy, Data Scientists Know All Your Secrets"](https://www.youtube.com/watch?v=X9jVjCVOUIM) (13 min video)
- **Lec 3** Capture Behavioral Engagement ["Marketing Automation for Higher Education"](https://www.youtube.com/watch?v=MjTZM7VQDzQ) (2 min video)
- Sara Buhr ["An Amazon Echo may be the key to solving a murder case"](https://techcrunch.com/2016/12/27/an-amazon-echo-may-be-the-key-to-solving-a-murder-case/) (3 min read)
- Emma Wollacott ["70,000 OkCupid Profiles Leaked, Intimate Details And All"](https://www.forbes.com/sites/emmawoollacott/2016/05/13/intimate-data-of-70000-okcupid-users-released/) (4 min read)
- CPAC New clip ["Clearview AI violated Canada's federal and provincial laws"](https://www.youtube.com/watch?v=czNTHe1rex8) (5 min video)

## Optional readings

<details><summary>Click to show</summary>

You don't have to read these before lab and you don't have to read all of them. The main reason for including them here is as a recommendation of where to deepen your knowledge if there is something that you find particularly interesting. I am giving a brief background to each so you can pick the ones that peak your interest.

- Minute Physics [Protecting Privacy with MATH](https://www.youtube.com/watch?v=pT19VwBAqKA)
  - Made when the US census switched to using differential privacy, includes more examples and intuition behind the concepts.
- Damien Desfontaines ["Differential privacy in (a bit) more detail"](https://desfontain.es/privacy/differential-privacy-in-more-detail.html)
  - A more technical explanation of differential privacy, including converting the coin flip example into the equations used when assessing privacy loss.
- Statistics Canada ["A Brief Survey of Privacy Preserving Technologies"](https://www.statcan.gc.ca/en/data-science/network/privacy-preserving)
  - Techniques that Canadian government is considering to use to protect your data better.
- Cynthia Dwork ["The Definition of Differential Privacy"](https://youtu.be/lg-VhHlztqo)
- Chris Gilliard ["Caught in the spotlight"](https://urbanomnibus.net/2020/01/caught-in-the-spotlight/)
- Richard Lai ["WiFi mesh networks can detect your breathing"](https://www.engadget.com/2017-10-09-origin-wireless-motion-detection-breathing-rate-sensor.html?)
  - [Fiction short story from Ken Liu on the same topic available here](https://www.dropbox.com/s/9dd19r172sk4m9a/Forever%20Magazine%20Issue%201.epub?dl=0) (I really recommend short stories from this author!)
- Glenn Greenwald ["Why privacy matters"](https://youtu.be/pcSlowAhvUk)
- Rachel Thomas ["Privacy and surveillance"](https://www.youtube.com/watch?v=HwfeDeqbmsI&)

</details>

## Submission instructions

rubric={mechanics:20}

<div class="alert alert-info">
<p>You receive marks for submitting your lab correctly, please follow these instructions:</p>

<ul>
  <li><a href="https://ubc-mds.github.io/resources_pages/general_lab_instructions/">
      Follow the general lab instructions.</a></li>
  <li><a href="https://github.com/UBC-MDS/public/tree/master/rubric">
      Click here to view a description of the rubrics used to grade the questions</a></li>
  <li>Push your <code>.ipynb</code> file to your GitHub repository for this lab (make at least three commits).</li>
  <li>Upload your <code>.ipynb</code> file to Gradescope.
  </li>
  <li>Include a clickable link to your GitHub repo for the lab just below this cell
    <ul>
      <li>It should look something like this https://github.ubc.ca/MDS-2022-23/DSCI_541_labX_yourcwl.</li>
      <li>If you are working in a group, you can create you own (public) repo in <a href="https://github.ubc.ca/MDS-2023-24"> the UBC-MDS organization</a> and link that instead.</li>
    </ul>
  </li>
<li>All your written answers must be in your own words.</li>
<li>You are not allowed to use generative AI tools to write your answers for you or simply paraphrase answer that you generate from these tools (that will lead to a failing grade), but you can use them to further understand the topics you are learning about.</li>
 
</ul>
</div>

[REPO LINK](https://github.com/UBC-MDS/DSCI_541_Lab2_SG)

## Overall writing quality

rubric={writing:20}

<div class="alert alert-info">

<p>You will receive an overall writing grade for the entire lab instead of for each question. This is just a small part of your total grade, but please use the Jupyter Lab spell checker extension to catch typos and read through your text for grammatical errors before submitting (or paste it into Google Docs/MS Word/Grammarly. You don't need to type anything under this cell, it is just a placeholder to generate the grading rubric.</p>
    
</div>

# 1. Short answer questions

Keep your replies brief, 1-3 sentences per question. Although these are short answer questions, don't copy answers from the readings, use your own words so that you practice learning these concepts. These will not be discussed during the lab.

## Question 1.1

rubric={reasoning:60}

<div class="alert alert-info">

<ol type="1">
<li>What is a data broker?</li>
<li>What are direct and indirect identifiers?</li>
<li>What is k-anonymity and l-diversity?</li>
<li>What are some weaknesses of k-anonymity (and l-diversity)? How could you re-identify individuals in these datasets?</li>
<li>If you have two differentially private datasets, one with and one without your data, what does differential privacy guarantee regarding your privacy?</li>
<li>How does differential privacy work on a conceptual level (watching the optional video from Minute Physics can help with this if you want more details and examples than what was given in the lecture)?</li>
<li>What are some additional approaches you could take to secure data stored in your organization?</li>
</ol>

</div>

YOUR ANSWERS HERE

1. A data broker is a company that collects/aggregates personal data from unknowing users and then sells that personal data to other companies (typically advertisers or recruiters).

2. Direct identifiers distinctly identify individuals through direct information such as their name or social security number while indirect identifiers indirectly reveal an individuals information, such as a zip code or birth date.

3. These are data anonymization approaches meant to protect user privacy. K-anonymity uses generalization and supression to hide a user within a crowd, while L-Diversity extends K-anonymity so that any sensitive attributes are represented multiple ways within a group to prevent re-identification.

4. One weakness of k-anonymity (and l-diversity) is called Homogeneity Attack: if all k individuals in a group have the same sensitive attribute, the anonymity does not work. Attackers could use other personal information to infer individual identities, as they all differ except for the sensitive attribute.

5. Differential privacy guarantees that any malicious actors cannot tell whether or not an individual's data was included/excluded from a dataset, due to plausible deniability.

6. Differential privacy works conceptually by adding specifically calibrated random noise to a dataset to ensure that any output is virtually identical, regardless of whether or not identifying information is present in that output. One flavour of this is called ε-Differential Privacy, which uses a specific Laplace mechanism for adding noise.

7. One additional approach is to use encryption or scrambling methods for direct and indirect identifiers: it is common to only use the first 3 characters in a zip code or to use proprietary encryption for primary keys, where actual identifiers (such as a primary health number) are completely replaced with a unique, random value.

# 2. Discussion questions

This section asks you to expand a bit on your reasoning, but still aim to write succinct replies around one paragraph per sub-question. The goal of lab discussions are not to provide you with the right answers, but to help your discussion along. Your TA will assist in this by bringing up topics that you might not have thought of, ask questions to break the silence or a dead end, and move the conversation along so that you have time to go through most questions. How useful the lab discussion is for your submission ultimately relies on that you actively contribute to the discussion and help your peers contribute and exchange ideas.

## Some tips to make your discussions in lab more effective

It is easy to overlook the flaws of our own reasoning,
so having a discussion with colleagues is an excellent opportunity
to develop your thinking and receive feedback
from someone who can provide an alternative perspective from your own.
Nevertheless,
many people don't know how to have an effective discussion,
so I am sharing a few tips for you to be able to make the most out of this opportunity:

- Commit to learning, not "winning" debates.
- Comment in order to share information and develop arguments further, not to persuade.
- Listen respectfully, without interrupting, to try to understand each others' views.
  - Don't focus on what you are going to say next while someone else is talking.
- Challenge ideas, not individuals.
  - And be open to having your own ideas challenged.
- Think about as good arguments as possible against your position.
  - This is especially useful if many of your peers have the same opinion, help your group find angles that you might otherwise be missing.
- Allow everyone the chance to speak.
  - Politely ask members of your group about their opinion.
- Avoid assumptions about any member of the class or generalizations about social groups.
  - Be careful about asking individuals to speak on the behalf of their (perceived) social group.
- Be aware of [logical fallacies](https://blog.hubspot.com/marketing/common-logical-fallacies), but avoid pointing them out in rude or disrespectful ways.

## Question 2.1 -- Technology and privacy

rubric={reasoning:100}

<div class="alert alert-info">

<ol type="1">

<li><b>Acceptable exchange.</b> Do you consider it acceptable that companies collect information about your online behavior in exchange for using their services? Is the service they provide a reasonable compensation of your data or do you think they owe you monetary compensation if they profit from selling your data to a third party? Include an example of a service you think provides a reasonable or unreasonable trade off.</li>
<li><b>Pay for privacy.</b> If you had the option would you pay to use email, social media, file storage, etc that met your preferred privacy standard? Are there specific online services which you would be more likely to pay for than others (and why do you think privacy is more important in these cases)? Is privacy a commodity that should only be available to those who can afford it, or is it a right that should be regulated and available to all for free?</li>

</ol>
</div>

OUTLINE SUBMITTED BY THE END OF THE LAB (if applicable)

1. reasonable, to a certain extent

- monetized through the user as a product (data collection for ads)
- otherwise we would have to pay
- ethical line: behaviour in the real world (e.g. mic/camera access), activity across other platforms
- outsourcing to third party companies can be scummy
- people do not read TOS, make it purposefully complicated, may be unknowingly consenting to supervision that is unethical
- companies should be held accountable re: extent of data useage
- there should be more transparency though about data collection and useage
- generally, people don't care and may see data privacy as a lost cause

2. depends on the utility of the service (more likely to pay for a confidential file storage or email service than a secure social media)

- privacy should be available to ALL, not just those who can afford to pay a fee
- in other cases, the user has the right to choose to sign up or participate in a service, they take on that burden for themselves
- needs a balance between privacy and total anonymity

FINAL OUTLINE

1.

2.

YOUR ANSWERS HERE: Rahiq

1.

2.

## Question 2.2 -- Technology and privacy

rubric={reasoning:100}

<div class="alert alert-info">

<ol>
<li><b>Terms of service.</b> When we sign up for online services, we often have to agree to terms of conditions to use the services. Sometimes these do indeed mention that your data is being collected by the company, but studies have shown that the language used in terms and conditions often requires college level reading apprehension, while many users of such platforms are children in middle and high school. Could you think of some ways to improve the presentation of terms of services to convey the information more effectively?</li>
<li><b>Alternative options.</b> A common argument is that we can just opt out of services we don't like and use others instead (i.e. it is the indvidual's responsibility), but is this really true? Or are we getting to the stage where we "need" certain online services for us to integrate in society and opting out is not really an option? For example, is there a widely used replacement alternative for services such as Facebook, Instagram, YouTube or TikTok that does not center their business model on mininig user information?</li>
<li><b>Beyond online tracking.</b> What about extending the data collection outside the online environment? Which of the following do you find reasonable and unreasonable privacy-wise? Are these examples different from tracking online (why/why not)?
<ul>
<li>Is it ok if an Amazon Echo/Google Home device records your voice at home?</li>
<li>What if you have friends over, do you need to inform them about your echo device and should their voices be recorded too?</li>
<li>What about a pair of glasses that automatically record video and sound as you walk around in public places?</li>
<li>Or using WiFi signals to detect people moving in their homes?</li>
</ul></li>
</ol>

</div>

OUTLINE SUBMITTED BY THE END OF THE LAB (if applicable)

1. We mentioned this in the discussion above

- recommend using an abstract or bullet points in clear deconstructed language highlighting the main areas of the TOS
- since companies are doing this on purpose, we need government regulation to enforce this contract
- add an FAQ to the TOS or in the main webpage
- chatbot to ask a question about the TOS

2. Depends on the exact service, some are definitely non-necessary for existence in modern society (YouTube, TikTok)

- some are pretty much essential like LinkedIn or an email service, can limit the amount of information you give them and be more mindful with your online footprint
- there is some individual responsibility though

3. None of these are reasonable or necessary to track offline behaviour (recording voice is not necessary and all parties should be informed)

- the issue with meta glasses is that it is much easier to hide the filming behaviour versus filming in public with a phone
- also individuals are much harder to hold accountable versus a company like Amazon allowing voice recordings
- in general, consent from all individuals (being recorded for a street interview, friends coming over) should be involved
- recording people in their homes is undoubtedly a bigger invasion of privacy compared to collecting data in public
- using WiFi signals is a purposefully invasive method of using WiFi (unrelated to its intended purpose) so this is undoubtedly unethical and malicious

FINAL OUTLINE

1.

2.

YOUR ANSWERS HERE: Amanpreet

1.

2.

3.

## Question 2.3 -- Scraping data and facial recognition software

rubric={reasoning:100}

<div class="alert alert-info">

<ol type="1">
<li><b>Facilitating queries on scraped data.</b> Is it fair game to scrape public information from the internet, and then facilitate queries on that information or are there any additional concerns when the data becomes easier to access? What about scraping data that is only public for anyone logged in to that platform but otherwise not accessible (e.g. Facebook or OKCupid) and then making it available outside the platform?</li>
<li><b>Privacy and control of scraped data.</b> Clearview AI is a company that provides facial recognition software, which is used by private companies, law enforcement agencies, universities and individuals. The database consists of more than three billion images scraped from the internet, including from social media applications. Clearview claims 99% accuracy for most photos and one of their goals is to find criminals more accurately than current approaches used by law enforcement. One of its biggest technical advantages over previous law enforcement tools is that they have a huge set of images including the general public, not just photos of previous convicts. <a href="https://openmedia.org/press/item/privacy-commissioners-find-police-use-of-clearview-ai-violated-privacy-rights-of-canadians">A recent data breach revealed that Clearview AI is employed among American and Canadian law enforcement, including by the Vancouver Police Department</a>.
<ul>
<li>How do you think such powerful facial recognition technology should be regulated? For example, is it fair use to scrape data that was public at the time of scraping and store it permanently in a database or do we have a <a href="https://en.wikipedia.org/wiki/Right_to_be_forgotten">a right to be forgotten</a> even in downloaded data? Should we take into consideration that they are using this data for a good cause, such as catching criminals (e.g. Clearview is claimed to have been used to identify participants in the Capitol hill riot and to identify dead soldiers in the Russia/Ukraine war)? Also think about how the scale of implementation matters, even for algorithms that are 99% accurate.</li>
</ul></li>
</ol>

</div>

OUTLINE SUBMITTED BY THE END OF THE LAB (if applicable)

1. It is fair game to scrape publicly available information from the internet and then facilitate querying

- this is where the accountability of the individual comes into play, where we assume all public information has been freely provided by the user
- long term data availability could become a concern as information on someone could become outdated and potentially be used against you, so perhaps easily queryed data should be limited to a certain time frame
- still fair game to scrape from a logged in account and make it accessible otherwise, assuming they are not set to private

2. Facial recognition is not free from the bias of its training data and specifically with law enforcement it is much more likely to find POC guilty of a crime compared to white people or to confuse racialized faces

- the consequences of a false alarm with this technology far outweigh the benefits
- also publically available facial datasets (trained on illegally scraped data) are questionable at all levels
- the secretive nature of it also makes it unethical
- on the flipside, it could be highly accurate and prevent future harm and speed up investigation
- could be used as a starting point to narrow down suspects rather than a convicting technology

3. it should be regulated, but it was fair to store data that was publicly scraped (the issue here is the data was illegally scraped)

- have to take benefits and consequences into consideration
- if Clearview is being used in criminal proceedings, there needs to be FULL transparency and the process/data used should be released to a court or legal team upon request

FINAL OUTLINE

1.

2.

YOUR ANSWERS HERE: Sean

1.

2.

3.

## Question 2.4 (Challenging)

rubric={reasoning:20}

<div class="alert alert-warning">
    
<p><em>Note: Since this exercise is a bit longer than the regular challenging questions, it will count <strong>both for the ~5% challenging points for this lab, and the 2% extra credit assignment for your overall grade in 541.</strong></em></p>
<p>In previous years, students have asked for an exercise on how to implement differential privacy in a data analysis. It’s difficult to fit this into the curriculum because many of the differential privacy libraries are not trivial to use and would take a fair amount of time to learn properly.</p>
<p>This challenging exercise is an experiment collaborated with the team behind <a href="https://www.antigranular.com/"> Antigranular</a>, a community-led open-source platform that combines confidential computing with differential privacy. They have put together a notebook with an introduction to a couple of differential privacy libraries that are easier to get started with. Antigranular is aiming to develop a general curriculum for privacy concerned data analysis, so as part of this exercise you will give feedback on how easy it was to follow along in the tutorial notebook and what you think could be improved.</p>
<p>You can <a href="https://github.ubc.ca/mds-2025-26/DSCI_541_priv-eth-sec_students/blob/master/Differential_Privacy_A_hands_on_introduction.ipynb">access the notebook in the student repo</a>. You can either study the output of the notebook without running it, or re-run the cells and change things around if you want to do more experimentation. You task is to read through the notebook and answer the following questions:</p>
<ol type="1">
<li>Why is the salary that is printed for the new employee so different when using differential privacy versus when we are not using it? Would you say this is a feature of differential privacy or a drawback?
</li>
<li>What does it mean that there is a tradeoff between privacy and utility? Describe this in the context of differential privacy specifically referring to the figure with the same name in the notebook and comment on why the size of the data matters.</li>
<li>Provide feedback on your general experience working through the notebook. What worked well and what do you think could be improved? Was it suitable for someone with your background level of experience with differential privacy (a brief high level introduction to the main concepts during lecture)? Did you find that seeing examples in actual code helpful for your understanding of what differential privacy is and how it can be employed in a data analysis?</li>
</ol>

</div>

YOUR ANSWERS HERE: Victoria

1.

2.

---

# Help us improve the labs

The MDS program is continually looking to improve our courses, including lab questions and content. The following optional questions will not affect your grade in any way nor will they be used for anything other than program improvement:

1. Approximately how many hours did you spend working or thinking about this assignment (including lab time)?

#Ans:

2. Were there any questions that you particularly liked or disliked?

#Ans: [Questions you liked]

#Ans: [Questions you disliked]
