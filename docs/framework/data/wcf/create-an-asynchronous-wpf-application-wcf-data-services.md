---
title: 'Procedura: creare un''applicazione Windows Presentation Framework asincrona (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e922ad20f9954a17f63f42559877f0a05a2ba1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>Procedura: creare un'applicazione Windows Presentation Framework asincrona (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è possibile associare i dati ottenuti da un servizio dati a elementi dell'interfaccia utente di un'applicazione Windows Presentation Framework (WPF). Per ulteriori informazioni, vedere [Binding di dati a controlli](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md). È anche possibile eseguire operazioni sul servizio dati in modo asincrono, che consente all'applicazione di continuare a rispondere durante l'attesa di una risposta a una richiesta di servizio dati. Per accedere al servizio dati in modo asincrono, è necessario disporre di applicazioni per Silverlight. Per ulteriori informazioni, vedere [operazioni asincrone](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 In questo argomento viene illustrato come accedere in modo asincrono a un servizio dati e associare i risultati agli elementi di un'applicazione WPF. Negli esempi riportati in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Tramite il codice XAML seguente viene definita la finestra dell'applicazione WPF.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>Esempio  
 La pagina code-behind seguente per il file XAML esegue una query asincrona usando il servizio dati e associa i risultati agli elementi nella finestra WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>Vedere anche  
 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
