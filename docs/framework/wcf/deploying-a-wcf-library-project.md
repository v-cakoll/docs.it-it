---
title: Distribuzione di un progetto Libreria di servizi WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbbbff1d88559f8ab35caa48fcb04ff1cd7bf015
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-a-wcf-library-project"></a>Distribuzione di un progetto Libreria di servizi WCF
Questo argomento descrive come distribuire un progetto Libreria di servizi [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## <a name="deploying-a-wcf-service-library"></a>Distribuzione di una libreria di servizi WCF  
 Una libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] è una libreria di collegamento dinamico (DLL, Dynamic Link Library). In quanto tale, non può essere eseguita autonomamente: deve essere distribuita in un ambiente host. Per ulteriori informazioni su questo processo, vedere [Hosting e l'utilizzo di servizi WCF](http://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Una libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] può essere distribuita come qualsiasi altro servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Tuttavia, occorre tenere presente che [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] non supporta la configurazione di DLL. <xref:System.Configuration> supporta un unico file di configurazione per ogni dominio applicazione. Il progetto Libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] riduce questa limitazione fornendo durante lo sviluppo un file per la libreria denominato App.config. Dopo la distribuzione, tuttavia, il file App.config non viene riconosciuto.  
  
 È necessario spostare il codice di configurazione nel file di configurazione riconosciuto dall'ambiente host utilizzato. Nel caso di servizi indipendenti, è necessario copiare il contenuto del file App.config nel file App.config del file eseguibile di hosting. Se per l'hosting del servizio si utilizza IIS, è necessario copiare il contenuto del file App.config nel file Web.config della directory virtuale.
