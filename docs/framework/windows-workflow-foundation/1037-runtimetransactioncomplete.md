---
title: 1037 - RuntimeTransactionComplete
ms.date: 03/30/2017
ms.assetid: 2c8c31e0-42a9-4f46-865b-2da9ab16a0ba
ms.openlocfilehash: 7a94c917157904c5cb84105c41842657a534c973
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509600"
---
# <a name="1037---runtimetransactioncomplete"></a>1037 - RuntimeTransactionComplete
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1037|  
|Parole chiave|WFRuntime|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che la transazione di runtime completata.  
  
## <a name="message"></a>Messaggio  
 Transazione di runtime completata con lo stato '%1'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Stato|xs:string|Lo stato della transazione.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
