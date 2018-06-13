---
title: Distribuzione di un progetto Libreria di servizi WCF
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: fb400a4d1ebba691222ad7fc9d2c09f1051591da
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803023"
---
# <a name="deploying-a-wcf-library-project"></a>Distribuzione di un progetto Libreria di servizi WCF
In questo argomento viene descritto come è possibile distribuire un progetto libreria di servizi Windows Communication Foundation (WCF).  
  
## <a name="deploying-a-wcf-service-library"></a>Distribuzione di una libreria di servizi WCF  
 Una libreria di servizi WCF è una libreria di collegamento dinamico (DLL). In quanto tale, non può essere eseguita autonomamente: deve essere distribuita in un ambiente host. Per ulteriori informazioni su questo processo, vedere [Hosting e l'utilizzo di servizi WCF](http://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Una libreria di servizi WCF può essere distribuita come qualsiasi altro servizio WCF. Tuttavia, occorre tenere presente che [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] non supporta la configurazione di DLL. <xref:System.Configuration> supporta un unico file di configurazione per ogni dominio applicazione. Il progetto di libreria di servizi WCF riduce questa limitazione fornendo un file app. config per la raccolta durante lo sviluppo. Dopo la distribuzione, tuttavia, il file App.config non viene riconosciuto.  
  
 È necessario spostare il codice di configurazione nel file di configurazione riconosciuto dall'ambiente host utilizzato. Nel caso di servizi indipendenti, è necessario copiare il contenuto del file App.config nel file App.config del file eseguibile di hosting. Se per l'hosting del servizio si utilizza IIS, è necessario copiare il contenuto del file App.config nel file Web.config della directory virtuale.
