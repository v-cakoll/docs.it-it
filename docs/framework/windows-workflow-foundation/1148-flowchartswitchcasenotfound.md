---
title: 1148 - FlowchartSwitchCaseNotFound
ms.date: 03/30/2017
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
ms.openlocfilehash: 7e96b5b7652d404e6fdbe2c04c6a4069ca78f20f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009916"
---
# <a name="1148---flowchartswitchcasenotfound"></a>1148 - FlowchartSwitchCaseNotFound
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|1148|  
|Parole chiave|WFActivities|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che non è stato trovato un case corrispondente o un case predefinito in un'opzione diagramma di flusso. L'esecuzione del diagramma di flusso terminerà.  
  
## <a name="message"></a>Messaggio  
 Diagramma di flusso '%1'/FlowSwitch: impossibile trovare un'attività Case o un case predefinito corrispondente al risultato dell'espressione. L'esecuzione del diagramma di flusso terminerà.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Diagramma di flusso|xs:string|Nome visualizzato del diagramma di flusso.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
