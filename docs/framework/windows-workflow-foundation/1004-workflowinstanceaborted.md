---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d34f6f1ab6af8e06a0f28fb043faf9fe16a8b211
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485187"
---
# <a name="1004---workflowinstanceaborted"></a>1004 - WorkflowInstanceAborted

## <a name="properties"></a>Proprietà

|||
|-|-|
|ID|1004|
|Parole chiave|WFRuntime|
|Livello|Informazioni|
|Canale|Microsoft-Windows-Application Server-Applications/Debug|

## <a name="description"></a>Descrizione

Indica che un'istanza del flusso di lavoro è stata interrotta con un'eccezione.

## <a name="message"></a>Messaggio

WorkflowInstance con ID: '%1' interrotta con un'eccezione.

## <a name="details"></a>Dettagli

|Nome elemento dati|Tipo elemento dati|Descrizione|
|--------------------|--------------------|-----------------|
|WorkflowInstanceId|`xs:string`|ID istanza del flusso di lavoro.|
|Eccezione|`xs:string`|Dettagli dell'eccezione.|
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
