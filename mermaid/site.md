---
title: Ansible Playbook Grapher
---
```mermaid
%%{ init: { "flowchart": { "curve": "bumpX" } } }%%
flowchart TD
	%% Start of the playbook '../playground/site.yml'
	playbook_3b1cf9c9("../playground/site.yml")
		%% Start of the play 'Play: webserver (1)'
		play_5f26124e["Play: webserver (1)"]
		style play_5f26124e fill:#c9032c,color:#ffffff
		playbook_3b1cf9c9 --> |"1"| play_5f26124e
		linkStyle 0 stroke:#c9032c,color:#c9032c
			%% Start of the role 'webserver'
			play_5f26124e --> |"1"| role_2239c29d
			linkStyle 1 stroke:#c9032c,color:#c9032c
			role_2239c29d("[role] webserver")
			style role_2239c29d fill:#c9032c,color:#ffffff,stroke:#c9032c
				task_0c3299cb[" webserver : Debug vars"]
				style task_0c3299cb stroke:#c9032c,fill:#ffffff
				role_2239c29d --> |"1 [when: hostvar01]"| task_0c3299cb
				linkStyle 2 stroke:#c9032c,color:#c9032c
				task_dd5242c2[" webserver : Debug some more"]
				style task_dd5242c2 stroke:#c9032c,fill:#ffffff
				role_2239c29d --> |"2"| task_dd5242c2
				linkStyle 3 stroke:#c9032c,color:#c9032c
				task_28383a0e[" webserver : Create html from template.j2"]
				style task_28383a0e stroke:#c9032c,fill:#ffffff
				role_2239c29d --> |"3"| task_28383a0e
				linkStyle 4 stroke:#c9032c,color:#c9032c
				%% Start of the role 'loadbalancer'
				role_2239c29d --> |"4"| role_2e324a8f
				linkStyle 5 stroke:#c9032c,color:#000000
				role_2e324a8f("[role] loadbalancer")
				style role_2e324a8f fill:#000000,color:#ffffff,stroke:#000000
					task_e26b4d66[" loadbalancer : Debug vars"]
					style task_e26b4d66 stroke:#000000,fill:#ffffff
					role_2e324a8f --> |"1"| task_e26b4d66
					linkStyle 6 stroke:#000000,color:#000000
				%% End of the role 'loadbalancer'
			%% End of the role 'webserver'
			%% Start of the role 'loadbalancer'
			play_5f26124e --> |"2"| role_2e324a8f
			linkStyle 7 stroke:#c9032c,color:#000000
			task_13e88890["[task]  Debug var"]
			style task_13e88890 stroke:#c9032c,fill:#ffffff
			play_5f26124e --> |"3"| task_13e88890
			linkStyle 8 stroke:#c9032c,color:#c9032c
		%% End of the play 'Play: webserver (1)'
		%% Start of the play 'Play: database (2)'
		play_3bf982cb["Play: database (2)"]
		style play_3bf982cb fill:#4902ca,color:#ffffff
		playbook_3b1cf9c9 --> |"2"| play_3bf982cb
		linkStyle 9 stroke:#4902ca,color:#4902ca
			%% Start of the role 'database'
			play_3bf982cb --> |"1"| role_11e0eed8
			linkStyle 10 stroke:#4902ca,color:#4902ca
			role_11e0eed8("[role] database")
			style role_11e0eed8 fill:#4902ca,color:#ffffff,stroke:#4902ca
				task_b6559cd0[" database : Debug vars"]
				style task_b6559cd0 stroke:#4902ca,fill:#ffffff
				role_11e0eed8 --> |"1"| task_b6559cd0
				linkStyle 11 stroke:#4902ca,color:#4902ca
				%% Start of the role 'loadbalancer'
				role_11e0eed8 --> |"2"| role_2e324a8f
				linkStyle 12 stroke:#4902ca,color:#000000
			%% End of the role 'database'
			%% Start of the role 'loadbalancer'
			play_3bf982cb --> |"2"| role_2e324a8f
			linkStyle 13 stroke:#4902ca,color:#000000
		%% End of the play 'Play: database (2)'
		%% Start of the play 'Play: loadbalancer (1)'
		play_fc1de41d["Play: loadbalancer (1)"]
		style play_fc1de41d fill:#34c10b,color:#ffffff
		playbook_3b1cf9c9 --> |"3"| play_fc1de41d
		linkStyle 14 stroke:#34c10b,color:#34c10b
			%% Start of the role 'loadbalancer'
			play_fc1de41d --> |"1"| role_2e324a8f
			linkStyle 15 stroke:#34c10b,color:#000000
		%% End of the play 'Play: loadbalancer (1)'
	%% End of the playbook '../playground/site.yml'
```