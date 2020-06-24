---
title: Accesso al servizio da un Web browser (Guida rapida di WCF Data Services)
description: Informazioni su come avviare WCF Data Services in Visual Studio e disabilitare la lettura del feed in un browser. Ottenere il documento di definizione del servizio e accedere alle risorse del servizio dati.
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: 713436c31bc3f622c4f44a83e33fff3fcbba1c1c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247778"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a>Accesso al servizio da un Web browser (Guida rapida di WCF Data Services)

Questa è la seconda attività del WCF Data Services avvio rapido. In questa attività si avvia il WCF Data Services da Visual Studio e, facoltativamente, si disabilita la lettura del feed nel Web browser. È quindi possibile recuperare il documento di definizione del servizio e accedere alle risorse del servizio dati inviando richieste HTTP GET tramite un Web browser alle risorse esposte.

> [!NOTE]
> Per impostazione predefinita, Visual Studio assegna automaticamente un numero di porta all'URI `localhost` del computer in uso. In questa attività viene usato il numero di porta `12345` negli URI di esempio. Per ulteriori informazioni su come impostare un numero di porta specifico nel progetto di Visual Studio, vedere [creazione del servizio dati](creating-the-data-service.md).

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a>Per richiedere il documento di servizio predefinito usando Internet Explorer

1. In Internet Explorer scegliere **Opzioni Internet**dal menu **strumenti** , fare clic sulla scheda **contenuto** , fare clic su **Impostazioni**e deselezionare **Attiva visualizzazione feed**.

     In questo modo viene disabilitata la lettura dei feed. Se non si disabilita questa funzionalità, anziché visualizzare i dati XML non elaborati, il browser considererà il documento con codifica AtomPub restituito come un feed XML.

    > [!NOTE]
    > Se nel browser non è possibile visualizzare il feed come dati XML non elaborati, dovrebbe ancora essere possibile visualizzarlo come codice sorgente per la pagina.

2. In Visual Studio premere il tasto **F5** per avviare il debug dell'applicazione.

3. Aprire un browser sul computer locale. Nella barra degli indirizzi digitare l'URI seguente:

    ```http
    http://localhost:12345/northwind.svc
    ```

     Verrà restituito il documento di servizio predefinito che contiene un elenco di set di entità esposti dal servizio dati.

## <a name="to-access-entity-set-resources-from-a-web-browser"></a>Per accedere alle risorse del set di entità da un browser

1. Nella barra dell'indirizzo del browser immettere l'URI seguente:

    ```http
    http://localhost:12345/northwind.svc/Customers
    ```

     Verrà restituito un set di tutti i clienti inclusi nel database Northwind di esempio.

2. Nella barra dell'indirizzo del browser immettere l'URI seguente:

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     Verrà restituita un'istanza di entità per il cliente specifico, `ALFKI`.

3. Nella barra dell'indirizzo del browser immettere l'URI seguente:

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     Verrà attraversata la relazione tra clienti e ordini per restituire un set di tutti gli ordini per il cliente specifico `ALFKI`.

4. Nella barra dell'indirizzo del browser immettere l'URI seguente:

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     Verranno filtrati gli ordini che appartengono al cliente specifico `ALFKI`, in modo che venga restituito solo un ordine specifico in base al valore `OrderID` fornito.

## <a name="next-steps"></a>Passaggi successivi

È stato eseguito l'accesso al WCF Data Services da un Web browser, con il browser che invia richieste HTTP GET alle risorse specificate. L'utilizzo di un browser consente di sperimentare il funzionamento della sintassi di indirizzamento delle richieste e visualizzare i risultati. L'accesso a un servizio dati di produzione non viene in genere eseguito mediante questo metodo. Di norma, le applicazioni interagiscono con il servizio dati tramite linguaggi di codice delle applicazioni o di script. Si creerà quindi un'applicazione client che utilizza librerie client per accedere alle risorse del servizio dati come se fossero oggetti CLR (Common Language Runtime):

> [!div class="nextstepaction"]
> [Creazione dell'applicazione client .NET Framework](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a>Vedere anche

- [Accesso alle risorse di un servizio dati](accessing-data-service-resources-wcf-data-services.md)
