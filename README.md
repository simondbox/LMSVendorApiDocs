# LMS Vendor Api Documentation

Details of all payloads with Request and Response Params

### /addLearningActivities (Master Import For Learning Activities)

#### Request Params

```
{
    "tenant_id": "",
    "learning_activity_code": "",
    "learning_activity_name": "",
    "learning_activity_description": "",
    "talent_vendor_code" "",
    "talent_program_code": "",
    "assign_to": [],
    "allow_search_to": [],
    "enrolled_to": [],
    "Currency": "",
    "cost": "",
    "available_from": "YYYY-MM-DD",
    "available_to": "YYYY-MM-DD",
    "content_link": "",
    "competencies_or_skills" : "",
    "competencies_or_skills_Code": "",
    "scale": "",
    "unenrolled_from": []
   
}
```

#### Response Params

``` 
{
  "status" : 1,
  "message" : "Successfully Added/Updated"
}

``` 
Error

``` 

{
  "status" : 0,
  "error" : "Message"
}

```

### /searchLearningActivity (To search activities in LMS Vendor)

#### Request Params

```JSON
{
    "user_id": "",
    "tenant_id": "",
    "term": "",
    "comp_id": [], 
    "skill_id": [], 
    "duration": "",
    "vendor_id": [], 
    "program_id": [],
}
```

#### Response Params

```
{
  results: [
      {
          learning_activity_code: '',
          learning_activity_id: '',
          learning_activity_name: '',
          learning_activity_description: '',
          vendor_code: '',
          vendor_name: '',
          vendor_id: '',
          program_id: '',
          program_code: '',
          program_name: '',
          assigned_to: '0/1',
          allow_search: 'Y/N',
          is_enrolled: 'Y/N',
          start_date: '',
          end_date: '',
          cost: '',
          rating_scale: 'Decimals',
          progress_status: '',
          enrollment_date: 'Date',
          completion_date: 'Date',
          competencies: [
              {
                  competency_id: '',
                  name: ''
              }
          ],
          skills: [
              {
                  skill_id: '',
                  name: ''
              }
          ]
      }
  ]
}
```

### /searchLearningPath (To search learning paths in LMS Vendor)

#### Request Params

```
{
    user_id: "",
    tenant_id: "",
    term: "",
    comp_id: "", // can select from dropdown list
    skill_id: "", // can select from dropdown list
    duration: "",
    vendor_id: "", // can select from dropdown list
    program_id: "", // can select from dropdown list
}
```

#### Response Params

```
{
  results: [
    {
        learning_plan_code: '',
        learning_plan_id: '',
        learning_plan_name: '',
        learning_plan_code: '',
        learning_plan_description: '',
        available_from: '',
        duration: '',
        assigned_to: '',
        searchable_by: '',
        cost: '',
        approval_workflow: '',
        enable_certificate: 'Y/N',
        certificate_template: '',
        enable_survey: '',
        survey_template: '',
        enable_sequential_flow: 'Y/N',
        vendor_code: '',
        vendor_id: '',
        vendor_name: '',
        program_id: '',
        program_code: '',
        program_name: '',
        allow_search: '',
        start_date: '',
        end_date: '',
        rating_scale: '',
        progress_status: '',
        is_enrolled: 'Y/N',
        enrollment_date: 'Date',
        completion_date: 'Date',
        learning_activity: [
            {
                activity_name: '',
                activity_id: '',
                vendor_code: '',
                vendor_id: '',
                program_id: '',
                vendor_name: '',
                program_code: '',
                program_name: '',
            }
        ],
        count_of_users_enrolled: '',
        count_of_users_completed: '',
        competencies: [
            {
                competency_id: '',
                name: '',
                competency_proficiency: ''
            }
        ],
        skills: [
            {
                skill_id: '',
                name: '',
                proficiency: ''
            }
        ]
    }
  ]
}
```

### /userEnrollment (To enrollment learning paths or activities in LMS Vendor)

#### Request Params

```
{
    user_id: "",
    tenant_id: "",
    enrollment_to: "learning_path/learning_activity",
    activity_or_plan_id: ""
}
```

#### Response Params

```
{
    message: 'Enrolled Successfully',
    enrollment_on: 'Date and Time'
}
```

### /userUnenrollment (To unenrollment learning paths or activities in LMS Vendor)

#### Request Params

```
{
    user_id: "",
    tenant_id: "",
    unenrollment_from: "learning_path/learning_activity",
    activity_or_plan_id: ""
}
```

#### Response Params

```
{
    message: 'Unenrolled Successfully',
    unEnrollment_on: 'Date and Time'
}
```

### /getLMSMaterDetails (To get all user details learning paths or activities in LMS Vendor)

#### Request Params

```
{
    tenant_id: "",
    user_id: ['userid1', 'userid2'] // optional
}
```

#### Response Params

```
{
    user_wise_details: [
        {
            user_id: '',
            learning_activities: [
                {
                    learning_activity_code: '',
                    learning_activity_id: '',
                    learning_activity_name: '',
                    learning_activity_description: '',
                    vendor_code: '',
                    vendor_name: '',
                    vendor_id: '',
                    program_id: '',
                    program_code: '',
                    program_name: '',
                    assigned_to: '0/1',
                    allow_search: 'Y/N',
                    is_enrolled: 'Y/N',
                    start_date: '',
                    end_date: '',
                    cost: '',
                    rating_scale: 'Decimals',
                    progress_status: '',
                    enrollment_date: 'Date',
                    completion_date: 'Date',
                    contains_assessment: 'Y/N',
                    assessment_status : '',
                    assessment_score: '',
                    competencies: [
                        {
                            competency_id: '',
                            name: '',
                            competency_proficiency: ''
                        }
                    ],
                    skills: [
                        {
                            skill_id: '',
                            name: '',
                            proficiency: ''
                        }
                    ]
                }
            ],
            learning_paths: [
                {
                    learning_plan_code: '',
                    learning_plan_id: '',
                    learning_plan_name: '',
                    learning_plan_description: '',
                    available_from: '',
                    duration: '',
                    assigned_to: '',
                    searchable_by: '',
                    cost: '',
                    approval_workflow: '',
                    enable_certificate: 'Y/N',
                    certificate_template: '',
                    enable_survey: '',
                    survey_template: '',
                    enable_sequential_flow: 'Y/N',
                    vendor_code: '',
                    vendor_id: '',
                    vendor_name: '',
                    program_id: '',
                    program_code: '',
                    program_name: '',
                    allow_search: '',
                    start_date: '',
                    end_date: '',
                    rating_scale: '',
                    progress_status: '',
                    is_enrolled: 'Y/N',
                    enrollment_date: 'Date',
                    completion_date: 'Date',
                    learning_activity: [
                        {
                            activity_name: '',
                            activity_id: '',
                            vendor_code: '',
                            vendor_id: '',
                            program_id: '',
                            vendor_name: '',
                            program_code: '',
                            program_name: '',
                            progress_status: '',
                            is_enrolled: 'Y/N',
                            enrollment_date: 'Date',
                            completion_date: 'Date',
                        }
                    ],
                    count_of_users_enrolled: '',
                    count_of_users_completed: '',
                    competencies: [
                        {
                            competency_id: '',
                            name: '',
                            competency_proficiency: ''
                        }
                    ],
                    skills: [
                        {
                            skill_id: '',
                            name: '',
                            proficiency: ''
                        }
                    ]
                }
            ],
            unique_competencies: [
                {
                    competency_id: '',
                    name: '',
                    competency_proficiency: ''
                }
            ],
            unique_skills: [
                {
                    skill_id: '',
                    name: '',
                    proficiency: ''
                }
            ],
            overview_on_learning_history: {
                sum_of_learning_activities: 'Number',
                overall_completion: 'In percentage',
                average_score: '',
                total_time_spent_on_learning: '',
            }
        }
    ]
}
```

