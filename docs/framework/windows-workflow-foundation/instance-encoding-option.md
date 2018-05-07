---
title: Instance Encoding Option
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: cfe45428f546b6f47709c321099efdf7fbb25ef4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="instance-encoding-option"></a>Instance Encoding Option
Il **Instance Encoding Option** proprietà dell'archivio di istanze del flusso di lavoro SQL consente di specificare se il provider di persistenza SQL deve comprimere le informazioni sullo stato di istanza del flusso di lavoro usando l'algoritmo GZip prima di salvare il informazioni nel database di persistenza. I valori consentiti per questa proprietà sono GZip e None. Il valore predefinito è None. Nell'elenco seguente vengono descritte queste opzioni.  
  
1.  **GZip**. Il provider di persistenza codifica le informazioni sullo stato usando l'algoritmo GZip prima di rendere persistenti le informazioni sullo stato nel database di persistenza.  
  
2.  **Nessuna**. Il provider di persistenza non codifica le informazioni sullo stato prima di salvare le informazioni nel database di persistenza.  
  
 La codifica delle informazioni sullo stato dell'istanza del flusso di lavoro tramite l'algoritmo GZip riduce il consumo di memoria nel database SQL e anche l'uso della rete se il database si trova in un computer della rete diverso dal computer in cui è in esecuzione l'host del servizio del flusso di lavoro. Una Guida generale consiste nell'impostare il **Instance Encoding Option** proprietà **Nessuno** se lo stato dell'istanza del flusso di lavoro è piccolo.
