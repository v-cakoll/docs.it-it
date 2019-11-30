---
title: "Procedura: creare un'applicazione Windows Presentation Framework asincrona (WCF Data Services)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
ms.openlocfilehash: 9bc1cef1f76e6e55e9cd5ed318741f8913abbaab
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569270"
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>Procedura: creare un'applicazione Windows Presentation Framework asincrona (WCF Data Services)
Con WCF Data Services è possibile associare i dati ottenuti da un servizio dati all'elemento dell'interfaccia utente di un'applicazione Windows Presentation Framework (WPF). Per ulteriori informazioni, vedere [associazione di dati a controlli](binding-data-to-controls-wcf-data-services.md). È anche possibile eseguire operazioni sul servizio dati in modo asincrono, che consente all'applicazione di continuare a rispondere durante l'attesa di una risposta a una richiesta del servizio dati. Per accedere al servizio dati in modo asincrono, è necessario disporre di applicazioni per Silverlight. Per altre informazioni, vedere [operazioni asincrone](asynchronous-operations-wcf-data-services.md).  
  
 In questo argomento viene illustrato come accedere in modo asincrono a un servizio dati e associare i risultati agli elementi di un'applicazione WPF. Negli esempi riportati in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono creati al completamento della [WCF Data Services avvio rapido](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Tramite il codice XAML seguente viene definita la finestra dell'applicazione WPF.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>Esempio  
 La pagina code-behind seguente per il file XAML esegue una query asincrona usando il servizio dati e associa i risultati agli elementi nella finestra WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
