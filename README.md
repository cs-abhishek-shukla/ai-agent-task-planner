# Release Information

- **Version**: 1.0.0

- **Certified**: Yes

- **Publisher**: Fortinet

- **Scope**: Core and Orchestration

- **Verified with Models**: Fortinet FortiAI (AI model Medium)

# Task Planner Agent

Analyzes user queries and assesses task scale and complexity. Generates optimized multi-step task plans by selecting and orchestrating the most appropriate tools to fulfill the objectives.

## Installation

This agent installs along with the FortiAI solution pack.

## Configuration

**Required MCP Servers**: NA

<!-- > [!Note]
>
> Refer to [Configuring MCP Servers](https://docs.fortinet.com/document/fortisoar/8.0.0/administration-guide/823139/mcp-servers#Configure_MCP_Servers) on FortiSOAR platform documentation for information on configuring a custom MCP server.
>  -->

### Prerequisites

- The FortiAI solution pack must be installed and configured with the Fortinet FortiAI connector.

  - To configure the FortiAI solution pack, refer to the [FortiAI](https://github.com/fortinet-fortisoar/solution-pack-fortinet-advisor/) solution pack documentation.
  - To configure the Fortinet FortiAI connector, refer to the [Fortinet FortiAI](https://docs.fortinet.com/fortisoar/connectors/fortinet-fortiai) connector documentation.

> [!Note]
>
> FortiAI solution pack and Fortinet FortiAI connector are preconfigured out-of-the-box with FortiSOAR `v8.0.0`.
> 


## Input Parameters

The input must be provided as a JSON object.

| Parameter          | Description                                                                                         |
|--------------------|-----------------------------------------------------------------------------------------------------|
| `query`            | User query that must be decomposed into structured, executable tasks.                               |
| `socrole`          | Defines the analyst role used to interpret the execution results and tailor response guidance.      |
| `chain_of_thought` | Logical reasoning that guides how the objective should be interpreted to retrieve the correct data  |
| `generate_plan`    | Set to `true` to generate a task execution plan; otherwise, decompose the task into actionable steps. |

## Response

The output is returned as a JSON object.

| Parameter          | Description                                                                        |
|--------------------|------------------------------------------------------------------------------------|
| `steps`            | A structured investigation plan composed of ordered steps.                         |
| `chain_of_thought` | When `generate_plan` is set to false, contains a structured breakdown of the task. |

