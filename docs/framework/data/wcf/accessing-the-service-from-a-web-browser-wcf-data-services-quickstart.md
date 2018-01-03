---
title: Accesso al servizio da un Web browser (Guida rapida di WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71beb254bf258da97207f14afca73cd68c6927ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a>Accesso al servizio da un Web browser (Guida rapida di WCF Data Services)
In questa attività si avvierà [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] da [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] e, in modo facoltativo, verrà disabilitata la lettura dei feed nel browser. Si verrà quindi recuperare il documento di definizione del servizio, nonché accedere alle risorse del servizio dati inviando richieste GET HTTP attraverso un browser Web alle risorse esposte.  
  
> [!NOTE]
>  Per impostazione predefinita, in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] viene assegnato automaticamente un numero di porta all'URI `localhost` sul computer in uso. In questa attività viene usato il numero di porta `12345` negli URI di esempio. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]come impostare un numero di porta specifico nel [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] progetto vedere [creazione del servizio dati](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
### <a name="to-request-the-default-service-document-by-using-internet-explorer"></a>Per richiedere il documento di servizio predefinito usando Internet Explorer  
  
1.  In Internet Explorer dal **strumenti** dal menu **Opzioni Internet**, fare clic su di **contenuto** scheda, fare clic su **impostazioni**e deselezionare  **Attivare la visualizzazione di lettura feed**.  
  
     In questo modo viene disabilitata la lettura dei feed. Se non si disabilita questa funzionalità, anziché visualizzare i dati XML non elaborati, il browser considererà il documento con codifica AtomPub restituito come un feed XML.  
  
    > [!NOTE]
    >  Se nel browser non è possibile visualizzare il feed come dati XML non elaborati, dovrebbe ancora essere possibile visualizzarlo come codice sorgente per la pagina.  
  
2.  In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] premere F5 per avviare il debug dell'applicazione.  
  
3.  Aprire un browser sul computer locale. Nella barra degli indirizzi digitare l'URI seguente:  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     Verrà restituito il documento di servizio predefinito che contiene un elenco di set di entità esposti dal servizio dati.  
  
### <a name="to-access-entity-set-resources-from-a-web-browser"></a>Per accedere alle risorse del set di entità da un browser  
  
1.  Nella barra dell'indirizzo del browser immettere l'URI seguente:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers  
    ```  
  
     Verrà restituito un set di tutti i clienti inclusi nel database Northwind di esempio.  
  
2.  Nella barra dell'indirizzo del browser immettere l'URI seguente:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')  
    ```  
  
     Verrà restituita un'istanza di entità per il cliente specifico, `ALFKI`.  
  
3.  Nella barra dell'indirizzo del browser immettere l'URI seguente:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders  
    ```  
  
     Verrà attraversata la relazione tra clienti e ordini per restituire un set di tutti gli ordini per il cliente specifico `ALFKI`.  
  
4.  Nella barra dell'indirizzo del browser immettere l'URI seguente:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643  
    ```  
  
     Verranno filtrati gli ordini che appartengono al cliente specifico `ALFKI`, in modo che venga restituito solo un ordine specifico in base al valore `OrderID` fornito.  
  
## <a name="next-steps"></a>Passaggi successivi  
 L'accesso a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] da un browser è stato eseguito correttamente, con il browser che invia richieste GET HTTP alle risorse specificate. L'utilizzo di un browser consente di sperimentare il funzionamento della sintassi di indirizzamento delle richieste e visualizzare i risultati. L'accesso a un servizio dati di produzione non viene in genere eseguito mediante questo metodo. Di norma, le applicazioni interagiscono con il servizio dati tramite linguaggi di codice delle applicazioni o di script. Si creerà quindi un'applicazione client che utilizza librerie client per accedere alle risorse del servizio dati come se fossero oggetti CLR (Common Language Runtime):  
  
 [Creazione dell'applicazione client .NET Framework](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Accesso alle risorse di un servizio dati](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
