Commands run using the Prolifics Code Profiler and Transformer tool...

../../as400-modernizer/dist/as400mod analyze -o ../docs/analysis_report/analysis_report.md  .

../../as400-modernizer/dist/as400mod components -o ../docs/components_report/components_report.md --visualize  .

../../as400-modernizer/dist/as400mod user-experience -o ../docs/user_experience_report/user_experience_report.md --visualize  .

../../as400-modernizer/dist/as400mod domain-model -o ../docs/domain_model_report/domain_model_report.md --visualize  .

../../as400-modernizer/dist/as400mod use-cases -o ../docs/use_cases_report/use_cases_report.md --include-scenarios  .

../../as400-modernizer/dist/as400mod code-review -o ../docs/code_review_report/code_review_report.md  .

../../as400-modernizer/dist/as400mod question  . "This code includes a dynamic menu feature - the menu is populated dynamically for a user based on their permissions, which is described in data. Can you see the data? If so, can you outline for me the dynamic menus that are available?"

../../as400-modernizer/dist/as400mod follow-up-question  . "OK, so if you can see the data, please give me a full list of the menu options desribed therein."

../../as400-modernizer/dist/as400mod follow-up-question  . "I looked at the MNUOPT file and I don't see any data. Explain. Are your examples made up examples or did you get from the file?"

../../as400-modernizer/dist/as400mod follow-up-question  . "In a previous answer you gave 'View Reports', 'User Management' and 'System Settings' as examples. Where did you get those from in the files? Were they made up examples?"

../../as400-modernizer/dist/as400mod extract-psm  . neo4j