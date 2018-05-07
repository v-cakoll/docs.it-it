---
title: Eccezioni host
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: f2bc7d0ca09faa2598990437295d1abf0cff3c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-exceptions"></a>Eccezioni host
In questo argomento vengono elencate tutte le eccezioni generate dall'host.  
  
## <a name="exception-list"></a>Elenco delle eccezioni  
  
|Codice risorsa|Stringa di risorsa|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|Non è consentito l'URI completo. Gli URI completi non sono consentiti per l'API ServiceHostingEnvironment.EnsureServiceAvailable. Usare un percorso virtuale per il servizio corrispondente.|  
|Hosting_BuildProviderCouldNotCreateType|Impossibile caricare il tipo CLR specificato durante la compilazione del servizio. Verificare che questo tipo viene definito in un file di origine all'interno dell'applicazione \\directory \App_Code, contenuti in un assembly compilato l'applicazione \\\bin directory o presenti in un assembly installato di Global Assembly Cache. Al nome del tipo viene applicata la distinzione tra maiuscole e minuscole. Le directory, ad esempio \\\App_Code e \\\bin deve trovarsi nella directory radice dell'applicazione. Il \\\App_Code e \\directory \bin non possono essere annidate nelle sottodirectory.|
