## Open AI Gym Distribution Center Environment for Multi Agent Co-ordination to deliver packages using optimal routes

#### Environment
- This open AI gym environments split the city into 8 regions using directions, 
- Each region will have one agent to make local delivery or hand of packages to other remote regions 
- Each region will be assgined with packages either to deliver locally or deliver the products to other 7 regions Distribution centres.     
- During every reset this environment randomly generate payload for every region for each agent.   0 is no load, 1 is load
- Each agent can move left, stay in the same location or move right. 
- During every action package will be handed off to remote region or delivered locally depending on the actions.     
- Rewards will be assigned based on the trip
    - if agent makes successful hand-off or local delivery reward 1 will be assigned, 
    - if agent makes a trip but doesn’t have package to hand off or locally delivery reward -1 will be assigned).  
- Task will be considered done once all the packages are delivered. 

#### Regions and transition  (refer action_state_transition.csv) 
- 8 regions and corresponding idx North-0, North East-1, East-2, South East-3, South-4, South West-5, West-6, North West-7
- When agent takes action 0 he moves to the left (anti clock direction) e.g if agent is in location North-0 and action is 0 agent moves to North West-7
- When agent takes action 1 he stays in the same location e.g if agent is in location North-0 and action is 1 agents new location remains same 0
- When agent takes action 2 he moves to the right (clock direction) e.g if agent is in location North-0 and action is 2 agent moves to North East-2
