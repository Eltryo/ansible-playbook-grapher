---
title: Ansible Playbook Grapher
---
```mermaid

%%{ init: { "flowchart": { "curve": "bumpX" } } }%%
flowchart TD
	%% Start of the playbook '../playground/site.yml'
	playbook_e8bd12b6("../playground/site.yml")
		%% Start of the play 'Play: webserver (1)'
		play_6bae9960["Play: webserver (1)"]
		style play_6bae9960 fill:#08a7c4,color:#ffffff
		playbook_e8bd12b6 --> |"1"| play_6bae9960
		linkStyle 0 stroke:#08a7c4,color:#08a7c4
			%% Start of the role 'webserver'
			play_6bae9960 --> |"1"| role_2239c29d
			linkStyle 1 stroke:#08a7c4,color:#08a7c4
			role_2239c29d("[role] webserver")
			style role_2239c29d fill:#08a7c4,color:#ffffff,stroke:#08a7c4
				task_4959ae99[" webserver : Debug vars"]
				style task_4959ae99 stroke:#08a7c4,fill:#ffffff
				role_2239c29d --> |"1 [when: hostvar01]"| task_4959ae99
				linkStyle 2 stroke:#08a7c4,color:#08a7c4
				task_c815c920[" webserver : Debug some more"]
				style task_c815c920 stroke:#08a7c4,fill:#ffffff
				role_2239c29d --> |"2"| task_c815c920
				linkStyle 3 stroke:#08a7c4,color:#08a7c4
				task_0ce35241[" webserver : Create html from template.j2"]
				style task_0ce35241 stroke:#08a7c4,fill:#ffffff
				role_2239c29d --> |"3"| task_0ce35241
				linkStyle 4 stroke:#08a7c4,color:#08a7c4
			%% End of the role 'webserver'
			task_ec9a106c["[task]  Debug var"]
			style task_ec9a106c stroke:#08a7c4,fill:#ffffff
			play_6bae9960 --> |"2"| task_ec9a106c
			linkStyle 5 stroke:#08a7c4,color:#08a7c4
		%% End of the play 'Play: webserver (1)'
		%% Start of the play 'Play: database (2)'
		play_f4cc702d["Play: database (2)"]
		style play_f4cc702d fill:#a92523,color:#ffffff
		playbook_e8bd12b6 --> |"2"| play_f4cc702d
		linkStyle 6 stroke:#a92523,color:#a92523
			%% Start of the role 'database'
			play_f4cc702d --> |"1"| role_11e0eed8
			linkStyle 7 stroke:#a92523,color:#a92523
			role_11e0eed8("[role] database")
			style role_11e0eed8 fill:#a92523,color:#ffffff,stroke:#a92523
				task_4c2cbaa2[" database : Debug vars"]
				style task_4c2cbaa2 stroke:#a92523,fill:#ffffff
				role_11e0eed8 --> |"1"| task_4c2cbaa2
				linkStyle 8 stroke:#a92523,color:#a92523
			%% End of the role 'database'
		%% End of the play 'Play: database (2)'
		%% Start of the play 'Play: loadbalancer (1)'
		play_84df7ed9["Play: loadbalancer (1)"]
		style play_84df7ed9 fill:#3b9176,color:#ffffff
		playbook_e8bd12b6 --> |"3"| play_84df7ed9
		linkStyle 9 stroke:#3b9176,color:#3b9176
		%% End of the play 'Play: loadbalancer (1)'
	%% End of the playbook '../playground/site.yml'
```