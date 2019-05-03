---
title: Eccezioni host
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: f2bc7d0ca09faa2598990437295d1abf0cff3c45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934732"
---
# <a name="hosting-exceptions"></a>Eccezioni host
In questo argomento vengono elencate tutte le eccezioni generate dall'host.  
  
## <a name="exception-list"></a>Elenco delle eccezioni  
  
|Codice risorsa|Stringa di risorsa|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|Non è consentito l'URI completo. Gli URI completi non sono consentiti per l'API ServiceHostingEnvironment.EnsureServiceAvailable. Utilizzare un percorso virtuale per il servizio corrispondente.|  
|Hosting_BuildProviderCouldNotCreateType|Impossibile caricare il tipo CLR specificato durante la compilazione del servizio. Verificare che questo tipo viene definito in un file di origine dell'applicazione \\directory \App_Code, contenuti in un assembly compilato l'applicazione \\\bin directory o presenti in un assembly installato di Global Assembly Cache. Al nome del tipo viene applicata la distinzione tra maiuscole e minuscole. Le directory, ad esempio \\\App_Code e \\\bin deve trovarsi nella directory radice dell'applicazione. Il \\\App_Code e \\directory \bin non possono essere annidate in sottodirectory.|
