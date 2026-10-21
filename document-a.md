Criteria A: Planning

Scenario
My client is Odgerel Manager, the school's activities coordinator. Right now, information about school clubs is scattered: some clubs are advertised on posters, some via messages, and others only by word of mouth. As a result, students do not know how many clubs exist or what each club does, and many are unaware of new or smaller clubs. In an informal survey of my classmates, no one could say how many clubs there currently are at our school, which shows that the existing system is ineffective for communicating club options.
Because of this, students miss opportunities to join clubs that match their interests, and some clubs struggle to recruit new members. There is also no simple, central place where a student can see if a club is open to new members, read detailed information, or request to join. New clubs are usually proposed by talking to a teacher or coordinator in person, which can be confusing for new students. Additionally, managing individual membership requests and updating club information would place unnecessary responsibilities on the activities coordinator.
My client and I agreed that a small, simple web-based solution listing all clubs in one place would solve this problem. The home page will display all available clubs and clearly show whether each is open or closed to new students. If a club is open, students can submit a join request through the site. Clicking on a club will show detailed information such as description, meeting time, room, teacher supervisor, and any requirements. Each club will have student representatives with administrator permissions, allowing them to manage membership requests, update club information, and change their club's availability status independently. In addition, there will be an option for students to propose a new club, which will send a request to the coordinator for approval. Odgerel Manager will mainly oversee club activities through a separate dashboard instead of handling individual requests and updates. The main goal is to make club information accessible and clear so students can easily discover clubs, see availability, and send requests without needing to ask around, while reducing the coordinator's administrative workload.

Justification
A web-based solution is suitable because it can be accessed on different devices through a browser without installing extra software. A website also allows the school to update club information in one central place instead of changing posters or sending repeated announcements. By giving student club representatives administrator permissions, the responsibility of updating club information and managing requests can be divided among individual clubs rather than relying entirely on the activities coordinator.
A database or structured data storage is needed to store club information such as club name, description, meeting time, teacher in charge, and whether the club is accepting new members. A simple relational database is appropriate because club records can be stored as rows and easily queried, filtered by "open/closed" status, and updated when club details change. The database will also store student accounts, membership requests, and administrator roles, allowing each club representative to manage only their assigned club. If a full database is not possible on the school servers, a lightweight alternative such as a JSON file or spreadsheet could be used initially, but a database is more scalable as the number of clubs grows.
The site will use HTML for page structure, Python for functionality, CSS for design, and JavaScript for interactive elements in the browser. On the server, FastAPI, a Python backend framework, will handle requests, manage the database, and process join or new club submissions. A relational database like PostgreSQL will store club data, user accounts, administrator permissions, and requests as records, making it easy to query by open or closed status. The system will use role-based access control to separate students, club administrators, and the activities coordinator. Club administrators will be able to manage their own clubs, including approving or rejecting membership requests and editing club information, while Odgerel Manager will be able to monitor all club activities without needing to manage everyday operations.
To ensure only students can submit join requests and to prevent external emails from registering, the system will validate email addresses using a regular expression (regex) that only accepts addresses ending in @shineue.edu.mn. Emails that do not match this pattern will be rejected with an error message. Email verification will also be used to confirm that students have access to their school accounts. Different permissions will be assigned depending on the user's role, ensuring that club administrators cannot modify other clubs' information and that only the activities coordinator has access to the overall management dashboard.


The site can be implemented using HTML, CSS, and JavaScript for the front end and a server-side language (for example, Java, Python, or JavaScript with Node.js) to handle requests, manage the database, and process join or new-club requests. A server-side language allows form submissions to be validated, stored, and possibly emailed or logged for the coordinator through an admin panel only accessible by the coordinator/admin. This approach also supports user input and dynamic updates to the club list, which a static website cannot handle effectively Regex: @shineue.edu.mn
Success criteria
The product will be considered successful if it meets the following measurable criteria:
Accessibility
The website can be opened and used on school computers and on common student devices via a web browser.
The main club list page is readable and navigable without needing to log in.
Functionality
The home page displays a list of all clubs currently offered at the school, including at least the club name and a brief description.
Each club in the list shows clearly whether it is “open” or “closed” to new members.
Clicking on a club opens a detailed view that includes longer description, meeting time, location, and teacher supervisor.
When a club is open, students can submit a “join request” form that records at least the student’s name, class/grade, and a short message.
There is a form that allows students to propose a new club, storing details such as proposed name, description, and teacher supervisor.
All club data and requests are stored in a persistent way so they are not lost when the server restarts.
The system prevents obviously incomplete submissions and displays a clear error message in these cases.
The activities coordinator can update club information and open/closed status without directly editing the code.


Information about school clubs is scattered across posters, announcements, messages, and word of mouth. There is no central platform where students can view all the clubs available at Shine Ue School. This makes it difficult for students to discover clubs that match their interests or find out whether they are accepting new members.  My client is Odgerel Manager, the school's activities coordinator, who is responsible for managing school club activities.
Students because have difficulty finding information about clubs and joining them. Club representatives because they struggle to advertise their clubs, recruit members, and update information. Club activity manager because they face difficulty organizing club information, managing requests, and approving new clubs.

The current system relies on posters, messages, and verbal communication. Posters cannot be updated easily, messages can be overlooked, and new students may not know whom to ask about clubs. Also, there is no organized method for submitting requests to join clubs or proposing new ones. This makes managing club activities less efficient for both students and the coordinator.

I will develop ClubHub, a platform that organizes all school clubs in one web. Students will be able to browse clubs, view detailed information, and check whether they are open, full, or closed. Registered students can submit join requests or propose new clubs.
Club representatives will be able to update their club information, while the Club Activity Manager will have administrative access to approve or reject new club submissions. The website will also be accessible through a QR code placed on school posters.



ClubHub should display 100% of the approved clubs stored in its database. Students should be able to view club information without logging in, but an account will be required to submit requests.
Each club page should display at least six pieces of information: name, description, meeting time, location, supervisor, and membership status.
The website should display its main club list within five seconds under normal school internet conditions. These requirements can be tested using sample club records and different devices.



ClubHub has several limitations:
Internet connection: The website() requires an internet connection to function.
Hosting: The system needs a computer or server to run the backend and database.
Time: Development and testing must be completed within the IA project period.
Data accuracy: Club information depends on representatives and the coordinator providing accurate details.
Email verification: Registration requires students to have access to their school email accounts.
Approval: New club submissions require manual approval from the Club Activity Manager.
 6. Shiidliin ajilah tsar hureeg bichij, yu hiihguig ch bs durdaj bolno
 ClubHub will focus on providing club information and managing membership and new club requests. The system will include student accounts, a club directory, detailed club pages, join request forms, club proposal forms, and administrative functions. However, ClubHub will not include an online payment system, attendance tracking, real-time messaging, or automatic club approval. It will also not display students' private information publicly.
These features are outside the project's main purpose and would increase development complexity. 

Computational context, scenarios yu yu ashiglah, programm -iin hereglee bichne (python), herhen ajiluulh, web baihu mobile baihu. 
SC-1 Students can register and log in using their school email addresses ending in @shineue.edu.mn Invalid email domains must be rejected.
SC-2 The homepage displays all approved clubs stored in the database, including their names, images, descriptions, and membership status.
SC-3 Students can select a club to view detailed information, including its activities, meeting time, location, supervisor, and availability.
SC-4 Registered students can submit membership requests to clubs marked as "Open". Requests must be saved in the database and displayed to the appropriate club administrator.
SC-5 Club administrators can approve or reject membership requests for their own clubs. The system must save and display the updated request status.
SC-6 Students cannot submit membership requests to clubs marked as "Full" or "Closed". An appropriate message must be displayed.
SC-7 Club administrators can edit their own club's information, including descriptions, meeting schedules, images, and membership status. The updated information must appear on the website after saving.
SC-8 The system prevents club administrators from modifying other clubs' information or processing their membership requests.
SC-9 Students can submit proposals for new clubs. Odgerel Manager can approve or reject these proposals and assign an initial club administrator when a proposal is approved.
SC-10 Odgerel Manager can access a dashboard displaying all approved clubs, their membership numbers, availability statuses, and submitted activity information without needing to process individual membership requests.

