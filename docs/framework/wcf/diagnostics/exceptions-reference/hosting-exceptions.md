---
title: Eccezioni host
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: efc22d39838caae4500a0673f5f86c3285134002
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-exceptions"></a>Eccezioni host
In questo argomento vengono elencate tutte le eccezioni generate dall'host.  
  
## <a name="exception-list"></a>Elenco delle eccezioni  
  
|Codice risorsa|Stringa di risorsa|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|Non è consentito l'URI completo. Gli URI completi non sono consentiti per l'API ServiceHostingEnvironment.EnsureServiceAvailable. Utilizzare un percorso virtuale per il servizio corrispondente.|  
|Hosting_BuildProviderCouldNotCreateType|Impossibile caricare il tipo CLR specificato durante la compilazione del servizio. Verificare che questo tipo viene definito in un file di origine all'interno dell'applicazione \\directory \App_Code, contenuti in un assembly compilato l'applicazione \\\bin directory o presenti in un assembly installato di Global Assembly Cache. Al nome del tipo viene applicata la distinzione tra maiuscole e minuscole. Le directory, ad esempio \\\App_Code e \\\bin deve trovarsi nella directory radice dell'applicazione. Il \\\App_Code e \\directory \bin non possono essere annidate nelle sottodirectory.|
