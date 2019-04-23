---
title: "Procedura: Abilitare l'accesso al servizio dati (WCF Data Services)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: d0a04cc38f1f57ef10e3b5065f9c476fd952050c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517755"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a>Procedura: Abilitare l'accesso al servizio dati (WCF Data Services)
In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è necessario concedere in modo esplicito l'accesso alle risorse esposte da un servizio dati. In altre parole, dopo aver creato un nuovo servizio dati, è necessario fornire in modo esplicito l'accesso alle singole risorse come set di entità. Questo argomento viene illustrato come abilitare la lettura e accesso in scrittura a cinque dell'entità vengono impostate nel servizio dati Northwind creato al completamento di [Guida introduttiva](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Poiché l'enumerazione <xref:System.Data.Services.EntitySetRights> viene definita tramite <xref:System.FlagsAttribute>, è possibile utilizzare un operatore logico OR per specificare più autorizzazioni per un solo set di entità.  
  
> [!NOTE]
>  I client che possono accedere all'applicazione ASP.NET saranno inoltre in grado di accedere alle risorse esposte dal servizio dati. Per impedire l'accesso non autorizzato alle risorse in un servizio dati di produzione, è inoltre necessario proteggere l'applicazione stessa. Per altre informazioni, vedere [protezione di siti Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/91f66yxt(v=vs.100)).  
  
### <a name="to-enable-access-to-the-data-service"></a>Per abilitare l'accesso al servizio dati  
  
-   Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]  
  
     In questo modo i client saranno in grado di accedere in lettura e scrittura ai set di entità `Orders` e `Order_Details` e solo in lettura ai set di entità `Customers`.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Sviluppare un servizio dati WCF in esecuzione in IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)
- [Configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
