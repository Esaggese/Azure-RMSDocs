---
title: class mip PolicyHandler 
description: Reference for class mip PolicyHandler 
author: BryanLa
ms.service: information-protection
ms.topic: reference
ms.date: 09/27/2018
ms.author: bryanla
---
# class mip::PolicyHandler 
This class provides an interface for all policy handler functions on a file.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
public std::shared_ptr<ContentLabel> GetSensitivityLabel(const ExecutionState& state)  |  Get the sensitivity label from existing content.
public std::vector<std::shared_ptr<Action>> ComputeActions(const ExecutionState& state)  |  Executes the rules in the handler based on the provided state and returns the list of actions to be executed.
 public void NotifyCommittedActions(const ExecutionState& state)  |  Called once the computed actions have been applied, and the data committed to disk.
  
## Members
  
### ContentLabel
Get the sensitivity label from existing content.

Parameters:  
* **state**: Current state of the content 



  
**Returns**: The label currently applied to the content. If not labeled, returns empty.
  
### Action
Executes the rules in the handler based on the provided state and returns the list of actions to be executed.

Parameters:  
* **state**: the current execution state of the content the rules are running on. 



  
**Returns**: List of actions that should be applied on the content.
  
### NotifyCommittedActions
Called once the computed actions have been applied, and the data committed to disk.

Parameters:  
* **state**: the current execution state of the content after the actions have been committed 


: This call sends an audit event