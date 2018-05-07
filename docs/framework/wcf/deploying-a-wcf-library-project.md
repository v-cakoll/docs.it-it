---
title: Distribuzione di un progetto Libreria di servizi WCF
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: 08a1d794aeeea1a41cd1eb3abf298f3f4a0f6d15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="deploying-a-wcf-library-project"></a>Distribuzione di un progetto Libreria di servizi WCF
In questo argomento viene descritto come è possibile distribuire un progetto libreria di servizi Windows Communication Foundation (WCF).  
  
## <a name="deploying-a-wcf-service-library"></a>Distribuzione di una libreria di servizi WCF  
 Una libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] è una libreria di collegamento dinamico (DLL, Dynamic Link Library). In quanto tale, non può essere eseguita autonomamente: deve essere distribuita in un ambiente host. Per ulteriori informazioni su questo processo, vedere [Hosting e l'utilizzo di servizi WCF](http://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Una libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] può essere distribuita come qualsiasi altro servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Tuttavia, occorre tenere presente che [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] non supporta la configurazione di DLL. <xref:System.Configuration> supporta un unico file di configurazione per ogni dominio applicazione. Il progetto Libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] riduce questa limitazione fornendo durante lo sviluppo un file per la libreria denominato App.config. Dopo la distribuzione, tuttavia, il file App.config non viene riconosciuto.  
  
 È necessario spostare il codice di configurazione nel file di configurazione riconosciuto dall'ambiente host utilizzato. Nel caso di servizi indipendenti, è necessario copiare il contenuto del file App.config nel file App.config del file eseguibile di hosting. Se per l'hosting del servizio si utilizza IIS, è necessario copiare il contenuto del file App.config nel file Web.config della directory virtuale.
