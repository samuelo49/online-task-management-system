# online-task-management-system
 ```
    Online Task Management System designed to empower users with seamless task management capabilities. This innovative application will include real-time updates, advanced analytics and reporting, a robust notification system, collaboration features, task tagging, and customizable attributes. 
 ```

# Core Requirements
    users: Handles user registration, authentication, and user roles.
    tasks: Manages tasks, task history, and task status.
    collaboration: Implements collaboration, group creation, and invitations.
    notifications: Manages the notification system.
    search: Implements search functionality.

# Models
users App
    - User Model
        - user_id
        - user_profile_picture 
        - user_bio
        - user_date_of_birth
        - is_Manager?
        - phone_number
        - address
        - city
        - state
        - zip_code
        - created_at
        - updated_at

    - UserGroup
        - name
        - description
        - members(list[User])
        - created_at
        - updated_at

tasks App
    - Task Model(model for tasks)
        - task_id
        - task_description
        - title
        - task_owner(FK:User)
        - task_assigned_to
        - task_created_on
        - task_due_date
        - task_completed_on
        - task_last_modified
        - task_notes
        - tags(ManyToMany with a seperate tags model)
        - priority

         
    - TaskHistory Model (model to track task history) with fields like task (ForeignKey to Task), status, and timestamp.)
    - Task Tagging Model(Implement task tagging using a ManyToManyField with a separate Tag model.)
    - Task Assignment (Allow task assignment by adding a field for assigned users or groups)

collabortion App
    - Group Model (Create model for groups, ManyToMany relationship with users for membership) 
    - Collaboration Model (collaboration between users and tasks)
