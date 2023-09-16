To present software architecture we decided the C4 model will be good enough as a way to help software development teams describe and communicate software architecture.  

## System context

A system context diagram provides a starting point, showing how the software system in scope fits into the world around it.  


![System context](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/system_context.png "a title")

## Container

A container diagram zooms into the software system scope, showing the high level technical building blocks. Presented blocks are independently deployable applications.  

![Container](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/container.png "a title")

## Dashboard Application Component

A dashboard application component diagram zooms into an idividual container, showing the components inside it. All components are connected to dashboard domain and share dashboard database schema in operational database.  

![Dashboard App Component](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/dashboard_app_component.png "a title")

## Analytical Application Component

An analytical application component diagram zooms into an idividual container, showing the components inside it. All components are connected to analytical domain and share analytical database.  

![Analytical App Component](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/analytical_app_component.png "a title")

## Trip Email Source Application Component

A trip email source application component diagram zooms into an idividual container, showing the components inside it. All components are connected to email source domain and share email source database schema in operational database.   

![Email App Component](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/trip_e-mail_source_app_component.png "a title")

## Travel System Integration Application Component

A travel system integration application component diagram zooms into an idividual container, showing the components inside it. All components are connected to travel systems domain and share travel system database schema in operational database. It is easy to extend this component by adding new connectors to new external travel systems to do the integration.   

![Travel System Integration App Component](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/trip_travel_source_connector_app_component.png "a title")

## Social Media Integration Application Component

A social media integration application component diagram zooms into an idividual container, showing the components inside it. All components are connected to social media domain. It is easy to extend this component by adding new connectors to new social media sources to do the integration.  

![Social Media Integration App Component](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/social_media_publisher_app_component.png "a title")

## Web Application Component

A web application component diagram zooms into an idividual container, showing the components inside it. The widget-based decomposition pattern was applied to create micro frontends architecture.  

![Web App Component](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/web_app_component.png "a title")

## Mobile Application Component

A mobile application component diagram zooms into an idividual container, showing the components inside it.  

![Mobile App Component](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/mobile_app_component.png "a title")

## Security Context

The security context diagram shows components involved in the authentication and authorization process. The Identity Provider Service manages user accounts.  

![Secirity Context](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/security_context.png "a title")

## Network Security Context

The network security context diagram shows components involved in the multi-layer network security architecture. It is worth to noting the use of a broker introduces an additional layer of protection because the active elements are processors, not the broker itself, so a request sent from outside does not directly affect its processing. The processor is the element that initiates communication, not an external service as is the case with direct network communication.  

Any traffic from the internet will go through a firewall to access the web server in the DMZ. Any traffic from the DMZ must also go through a firewall to access the internal network. This can be the same firewall with a separate interface and access control list, however, it could be two physically separate firewalls.  

![Network Secirity Context](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/network_security_context.png "a title")

## Deployment Diagram

A deployment diagram allows to illustrate how instances of software systems and/or containers in the static model are deployed on the infrastructure within given deployment environment (presented for single datacenter deployment, all datacenters have twin deployments). Users devices connects to the system by a load balancing service. Load balancers distribute a set of tasks over a set of resources (computing units). Processing components (have 'process' word in their names) included in independently deployable applications scale in and out as a whole application using built-in broker mechanisms and operational level nodes management. Scaling takes place at the level of a separate domain (represented by independently deployable application).  

![Deployment Diagram](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/deployment_diagram.png "a title")

[Go back](../../README.md)