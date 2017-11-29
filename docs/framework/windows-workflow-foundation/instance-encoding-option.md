---
title: Instance Encoding Option
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5803b034eeecac66aa20951c5167b9e666f1fa8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="instance-encoding-option"></a>Instance Encoding Option
Il **Instance Encoding Option** proprietà dell'archivio di istanze del flusso di lavoro SQL consente di specificare se il provider di persistenza SQL deve comprimere le informazioni sullo stato di istanza del flusso di lavoro usando l'algoritmo GZip prima di salvare il informazioni nel database di persistenza. I valori consentiti per questa proprietà sono GZip e None. Il valore predefinito è None. Nell'elenco seguente vengono descritte queste opzioni.  
  
1.  **GZip**. Il provider di persistenza codifica le informazioni sullo stato usando l'algoritmo GZip prima di rendere persistenti le informazioni sullo stato nel database di persistenza.  
  
2.  **Nessuna**. Il provider di persistenza non codifica le informazioni sullo stato prima di salvare le informazioni nel database di persistenza.  
  
 La codifica delle informazioni sullo stato dell'istanza del flusso di lavoro tramite l'algoritmo GZip riduce il consumo di memoria nel database SQL e anche l'uso della rete se il database si trova in un computer della rete diverso dal computer in cui è in esecuzione l'host del servizio del flusso di lavoro. Una Guida generale consiste nell'impostare il **Instance Encoding Option** proprietà **Nessuno** se lo stato dell'istanza del flusso di lavoro è piccolo.
