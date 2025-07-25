description: 
use parallel task tool calls to complete the specified task "$ARGUMENTS" each task tool should operate independently and in parrelel to execute complex development tasks efficiently.

allowed-tools:

task

spawn between 3 and 10 specialized parrelel task tools (subagents) to handle "$ARGUMENTS" efficiently through parallel execution.

## Instructions:
1. **Parse the request**: Break down "$ARGUMENTS" into logical, independent work units
2. **Create specialized agents**: Each task tool (subagent) should have a specific domain of responsibility  
3. **Ensure autonomy**: Each subagent should be self-contained with clear deliverables
4. **Optimize for parallelism**: Tasks should be designed to run simultaneously without dependencies
5. **Provide clear scope**: Give each agent specific files, functions, or areas to focus on

## Task Distribution Strategy:
- **File-based division**: Assign different files or modules to different agents
- **Feature-based division**: Split by functionality or components 
- **Layer-based division**: Separate by concerns (tests, docs, implementation, etc.)
- **Tool-based division**: Assign based on different tool specializations

## Agent Instructions Template:
For each task tool call, provide:
- **Specific objective**: What exactly should this agent accomplish
- **Scope boundaries**: Which files, directories, or components to work on
- **Expected deliverables**: What concrete outputs are expected
- **Context needed**: Any prerequisites or background information
- **Success criteria**: How to know the task is complete

Execute the parallel task tool (subagent) strategy for: $ARGUMENTS

