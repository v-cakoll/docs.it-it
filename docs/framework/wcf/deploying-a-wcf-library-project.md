---
title: Distribuzione di un progetto Libreria di servizi WCF
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: 186ce5ae3087fd9b4c7e5c32e110de4bc7d5e578
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801991"
---
# <a name="deploying-a-wcf-library-project"></a>Distribuzione di un progetto Libreria di servizi WCF
In questo argomento viene descritto come distribuire un progetto di libreria di servizi Windows Communication Foundation (WCF).  
  
## <a name="deploying-a-wcf-service-library"></a>Distribuzione di una libreria di servizi WCF  
 Una libreria di servizi WCF è una libreria di collegamento dinamico (DLL). In quanto tale, non può essere eseguita autonomamente: deve essere distribuita in un ambiente host. Per ulteriori informazioni su questo processo, vedere [hosting e utilizzo di servizi WCF](https://docs.microsoft.com/previous-versions/dotnet/articles/bb332338(v=msdn.10)).  
  
 Una libreria di servizi WCF può essere distribuita come qualsiasi altro servizio WCF. Tuttavia, tenere presente che .NET Framework non supporta la configurazione per le dll. <xref:System.Configuration> supporta un unico file di configurazione per ogni dominio applicazione. Il progetto libreria di servizi WCF attenua questa limitazione fornendo un file app. config per la libreria durante lo sviluppo. Dopo la distribuzione, tuttavia, il file App.config non viene riconosciuto.  
  
 È necessario spostare il codice di configurazione nel file di configurazione riconosciuto dall'ambiente host utilizzato. Nel caso di servizi indipendenti, è necessario copiare il contenuto del file App.config nel file App.config del file eseguibile di hosting. Se per l'hosting del servizio si utilizza IIS, è necessario copiare il contenuto del file App.config nel file Web.config della directory virtuale.
