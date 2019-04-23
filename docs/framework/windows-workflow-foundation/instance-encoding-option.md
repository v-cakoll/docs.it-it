---
title: Instance Encoding Option
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: c4de7c45d899f45a7b5b71d563257d9accb8fdbb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773844"
---
# <a name="instance-encoding-option"></a>Instance Encoding Option
Il **Instance Encoding Option** proprietà la Store di istanza del flusso di lavoro SQL consente di specificare se il provider di persistenza SQL deve comprimere le informazioni sullo stato di istanza del flusso di lavoro usando l'algoritmo GZip prima del salvataggio il informazioni nel database di persistenza. I valori consentiti per questa proprietà sono: GZip e None. Il valore predefinito è None. Nell'elenco seguente vengono descritte queste opzioni.  
  
1. **GZip**. Il provider di persistenza codifica le informazioni sullo stato usando l'algoritmo GZip prima di rendere persistenti le informazioni sullo stato nel database di persistenza.  
  
2. **Nessuno**. Il provider di persistenza non codifica le informazioni sullo stato prima di salvare le informazioni nel database di persistenza.  
  
 La codifica delle informazioni sullo stato dell'istanza del flusso di lavoro tramite l'algoritmo GZip riduce il consumo di memoria nel database SQL e anche l'uso della rete se il database si trova in un computer della rete diverso dal computer in cui è in esecuzione l'host del servizio del flusso di lavoro. Un materiale sussidiario generale consiste nell'impostare il **Instance Encoding Option** proprietà **None** se lo stato dell'istanza del flusso di lavoro è piccolo.
