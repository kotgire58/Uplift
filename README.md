# Overview

The project, titled "Uplift:Skills to Opportunities", aims to tackle the multifaceted challenges faced by youth today, emphasizing education, employment, and active societal engagement. Recognizing the pivotal role young individuals play in shaping the future, Uplift seeks to empower them through a comprehensive suite of programs and initiatives that foster personal and professional development. The project operates on several core principles: inclusivity, accessibility, and sustainability, ensuring that the opportunities it provides are equitable and have a lasting impact.

# Features

## User Authentication

Uplift empowers your learning journey with seamless authentication options. Log in effortlessly using your GitHub or Google credentials, or opt for traditional email-based access. Dive into a universe of knowledge with a single click, and join a community where technology education meets convenience.

## Courses

Uplift's course catalog features a meticulously curated list, presenting a spectrum of learning opportunities tailored to cater to a variety of interests and skill levels. From cutting-edge technology trends to foundational IT skills, each course is designed to empower learners on their quest for knowledge and professional growth.

## Admin

The Uplift admin panel is a powerhouse of functionality, designed for streamlined management and oversight. Admins have the privilege to not only add new courses but also refine course titles, ensuring that the educational content remains relevant and up-to-date. Additionally, the panel provides insightful analytics, offering a clear view of course performance and learner engagement, enabling informed decisions to enhance the learning experience.

## Analytics

The Uplift analytics dashboard transforms data into visual stories, with intuitive charts mapping the educational journey of learners and the success of courses. This interface meticulously tracks and displays order trends, sign-ups, and engagement levels, offering a comprehensive snapshot of growth and areas ripe for expansion. It's an essential tool for strategic decision-making and fostering a data-driven learning environment.

## Orders

In Uplift's dynamic admin console, the 'Orders' section provides a real-time feed of course enrollments, enabling administrators to monitor new sign-ups as they happen. This up-to-the-minute data stream serves as a pulse on the platform's traction and growth, offering valuable insights into learner demand and operational scalability.

## Email Notification

Uplift's automated system ensures that every new user registration triggers a tailored email notification, providing administrators with immediate updates. Additionally, for enhanced security and user verification, the system dispatches a One-Time Password (OTP) directly to the new registrant's email, streamlining the authentication process while maintaining rigorous standards of user data protection.

## Tech Stack

Below is a table summarizing the technologies used in our project:

| Layer         | Technology       | Description                                                                                     |
|---------------|------------------|-------------------------------------------------------------------------------------------------|
| **Frontend**  | Next.js          | React framework for server-side rendering and static website generation.                        |
| **Backend**   | Node.js          | Asynchronous JavaScript runtime for scalable network applications.                              |
|               | Express.js       | Web application framework for Node.js, designed for building web applications and APIs.         |
| **Caching**   | Redis            | In-memory data structure store, used as database cache and message broker.                      |
| **State Management** | Redux Toolkit (RTK) Query | Data fetching and caching toolkit for efficient state management.         |
| **Styling**   | Tailwind CSS     | Utility-first CSS framework for designing directly in the markup.                               |
| **Mailing**   | EJS              | Templating engine to generate email templates with dynamic data.                                |
| **Database**  | MongoDB          | NoSQL database for flexible data storage and management.                                        |

## To Run Project

Make sure you have Node.js And MongoDB installed
`npm i`

Type in Terminal:
Client- `npm run dev` 
Server- `npm run dev`

# Object Model

```
classDiagram

    class YouthMember {
      +Integer ID
      +String Name
      +Integer Age
      +String Email
      +String Gender
      +String EducationLevel
      +String EmploymentStatus
      +String Location
      +Integer FamilyGrossIncome
      +String FieldOfInterest
    }

    class CoursesAvailable {
      +Integer ID
      +String Name
      +String Description
      +String TypeOfField
      +String Prerequisite
    }

    class CourseRegistration {
        +Integer ID
        +String CourseName
        +String Duration
        +String FacultyName
        +Integer SeatsAvailable
    }

    class EmploymentOpportunity {
      +Integer ID
      +String Name
      +String CompanyName
      +String Description
      +String Requirements
      +String Industry
      +Integer Salary
      +String ApplicationURL
    }

    class Company {
      +String Name
      +String Location
      +String URL
      +String Industry
    }

    class GenderEqualityInitiative {
      +Integer ID
      +String Name
      +String Description
      +String TargetAudience
      +String Goals
    }

    class MentorshipProgram {
      +Integer MentorID
      +String MentorName
      +String ExpertiseArea
      +String Availability
      +Integer MenteeID
    }

    class YouthEngagementActivities {
      +Integer ActivityID
      +String Name
      +String Description
      +String Location
      +String Schedule
      +Integer ParticipantID
    }

    class SkillAssessment {
      +Integer AssessmentID
      +Integer YouthMemberID
      +String SkillName
      +Integer Score
      +String Feedback
    }

    class CommunityProjects {
      +Integer ProjectID
      +String Name
      +String Description
      +String Objective
      +String Location
      +String Impact
    }

    class ProjectSponsors {
      +Integer SponsorID
      +String Name
      +String Type  // Individual, Company, or Organization
      +String InterestAreas
      +String SupportType  // Funding, Mentorship, Resources, etc.
      +String ContactInfo
    }

    class FeedbackAndOutcomesTracking {
      +Integer FeedbackID
      +Integer YouthMemberID
      +Integer ProgramID
      +String Comments
      +String OutcomeMetrics
    }

    YouthMember "n" -- "m" CoursesAvailable : enrolls in
    YouthMember "n" -- "m" EmploymentOpportunity : qualifies for
    YouthMember "n" -- "m" GenderEqualityInitiative : participates in
    CommunityProjects "n" -- "m" MentorshipProgram : includes
    YouthMember "n" -- "m" YouthEngagementActivities : joins
    YouthMember "n" -- "1" SkillAssessment : undergoes
    YouthMember "n" -- "m" CommunityProjects : contributes to
    CommunityProjects "n" -- "m" ProjectSponsors : supported by
    YouthMember "1" -- "1" FeedbackAndOutcomesTracking : provides feedback on
    CoursesAvailable "n" -- "1" CourseRegistration : leads to
    EmploymentOpportunity "n" -- "m" Company : offered by

```
