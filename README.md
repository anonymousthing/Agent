Agent
=====

An agent server for the nodejs implementation of the iLab Shared Architecture

For more information, please see the [instruction manual](http://www.samuco.net/ilab/manual.pdf)

###Purpose
An agent is designed to provide a way of ‘modifying broker behaviour’ without making any changes to the broker source code. This is useful for access control and keeping the system stable. The agent is designed to work with [modern service brokers](https://github.com/ShadovvMoon/Broker)

All actions supported by the broker are also supported by the agent. The most basic agent acts as a wrapper for commands (simply passing commands through to the broker). A more advanced agent could introduce logic inside commands or other authentication systems.

###Installation
```
cd <path to agent directory>
npm install
node index.js
```

Press return or enter to start the interactive agent setup process. Some additional information about the setup prompts are included below.

**Port (for this agent)**
- This is the port that the agent will run on. You can either type in a port or leave it blank and have an open port between 2000 and 10000 automatically picked.

**Broker Host**
- This is the hostname for the server that the service broker runs on. 

**Broker Port**
- This is the port number that the service broker runs on. 

**Agent GUID**
- This is the unique identifier for the agent which must correspond to the agent ‘GUID’ field in the service broker admin interface. If no corresponding agent exists on the service broker, you will not be able to complete the setup process until one does.

**Agent Passkey**
- This is the passkey for the agent which must correspond to the agent ‘Passkey’ field in the service broker admin interface.

**Does this agent need experiment results (y/n)?**
- This option enables the dual channel mode. This mode is important if you to receive notifications from lab servers and brokers. See sections 4.5.1 and 4.5.2 of the [instruction manual](http://www.samuco.net/ilab/manual.pdf)

###Command line interface
The command line interface supports the commands  below (you can also type in the help command to show this information).

```
>>> help
commands
  connect - connect to the broker
  test - get some details about this agent from the broker
 
  stop - stop the agent
 
  set [key] [value] - modify configuration settings
  get [key] - retrieve configuration settings
  config - retrieve all configuration settings
 
  plugins - show a list of plugins
  enable [plugin] - enable a plugin
  disable [plugin] - disable a plugin (requires server restart)
  config [plugin] - retrieve all configuration settings for a plugin
  set [plugin] [key] [value] - modify configuration settings for a plugin
  get [plugin] [key] - retrieve configuration settings for a plugin
 
configuration keys
  is_simple     - [true/false]
  agent_host    - agent hostname
  agent_port    - agent port
  agent_uid     - agent guid
  agent_key     - agent passkey
  broker_url    - broker hostname
  broker_port   - broker port
  verbose       - show verbose logging
  show_requests - show express requests
```
