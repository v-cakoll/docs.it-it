---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 752cd73066c3c15ecbb36c40c417ee84b3fcf184
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756091"
---
# <a name="3502---inferredoperationdescription"></a>3502 - InferredOperationDescription
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|3502|  
|Parole chiave|WFServices|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Indica che OperationDescription è stato dedotto da WorkflowService.  
  
## <a name="message"></a>Messaggio  
 OperationDescription con Name= '%1'' nel contratto '%2' dedotta da WorkflowService. IsOneWay=%3.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|Nome dell'operazione.|  
|ContractName|xs:string|Nome del contratto.|  
|IsOneWay|xs:string|True o False che indica se il contratto è unidirezionale.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
