# aws_agent

#### Table of Contents

1. [Description](#description)
1. [Setup - The basics of getting started with ssm_agent](#setup)
    * [What ssm_agent affects](#what-ssm_agent-affects)
    * [Setup requirements](#setup-requirements)
    * [Beginning with ssm_agent](#beginning-with-ssm_agent)
1. [Usage - Configuration options and additional functionality](#usage)
1. [Reference - An under-the-hood peek at what the module is doing and how](#reference)
1. [Limitations - OS compatibility, etc.](#limitations)
1. [Development - Guide for contributing to the module](#development)

## Description

The aws agent module installs, configures, and manages the AWS aws agent service across a range of operating systems and distributions.

## Setup

### Beginning with aws_agent

`include '::aws_agent'` is enough to get you up and running.

## Usage

All parameters for the ntp module are contained within the main `::aws_agent` class, so for any function of the module, set the options you want. See the common usages below for examples.

### Install and enable AWS Agent

```puppet
include '::aws_agent'
```

## Reference

### Classes

#### Public classes

* aws_agent: Main class, includes all other classes.

#### Private classes

* aws_agent::install: Handles the packages.
* aws_agent::service: Handles the service.

## Parameters

The following parameters are available in the `::aws_agent` class:

#### `aws_agent_url`

Optional.

Data type: String.

The ssm agent download url

Default value: `https://s3.amazonaws.com/ec2-downloads-windows/SSMAgent/latest/$OS_VER/amazon-ssm-agent.{dev,rpm}`.

#### `aws_agent_download_url`

Optional.

Data type: String.

The ssm agent download url

Default value: `https://d1wk0tztpsntt1.cloudfront.net/linux/latest/install`

#### `proxy_install_manage`

Optional.

Data type: Boolean.

Enables the use of agents to download the source code

Default value: `false`

#### `proxy_install_manage_timeout`

Optional.

Data type: String.

Connect timeout use of agents to download the source code

Default value: `3`