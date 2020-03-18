---
title: WCF Web Service Reference Provider
description: Panoramica dello strumento Microsoft WCF Web Service Reference Provider che aggiunge funzionalità per i progetti .NET Core e ASP.NET Core, come Aggiungi riferimento al servizio per i progetti .NET Framework.
author: dasetser
ms.date: 10/29/2019
ms.custom: mvc
ms.openlocfilehash: cdd6b457d289dd7b752c97c5645f0797f24b72aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715676"
---
# <a name="use-the-wcf-web-service-reference-provider-tool"></a>Usare lo strumento WCF Web Service Reference Provider

Nel corso degli anni, molti sviluppatori di Visual Studio hanno aumentato la produttività usando lo strumento [**Aggiungi riferimento al servizio**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) quando era necessario che i progetti .NET Framework accedessero ai servizi Web.  Lo strumento **WCF Web Service Reference Provider** è un'estensione WCF Connected Service di Visual Studio che offre esperienza simile alla funzionalità Aggiungi riferimento al servizio per i progetti .NET Core e ASP.NET Core. Questo strumento consente di recuperare metadati da un servizio web nella soluzione corrente, in un percorso di rete o da un file WSDL e genera un file di origine compatibile con .NET Core contenente codice del proxy client Windows Communication Foundation (WCF) che è possibile usare per accedere al servizio Web.

> [!IMPORTANT]
> Si consiglia di fare riferimento solo a servizi provenienti da un'origine attendibile. L'aggiunta di riferimenti da un'origine non attendibile può compromettere la sicurezza.

## <a name="prerequisites"></a>Prerequisites

- [Visual Studio 2017 versione 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) o versioni successive

## <a name="how-to-use-the-extension"></a>Come usare l'estensione

> [!NOTE]
> L'opzione **WCF Web Service Reference** è applicabile ai progetti creati con i modelli di progetto seguenti:
>
> - **Visual C#** > Componenti di base di Visual C **.NET**
> - **Standard** > di Visual C **.NET**
> - **Visual C#** Applicazione > **Web di** > **base ASP.NET di** Visual C

Se si usa il modello di progetto **Applicazione ASP.NET Core Web**, l'articolo illustra i passaggi per aggiungere un riferimento al servizio WFC al progetto:

1. In Esplora soluzioni fare doppio clic sul nodo **Servizi connessi** del progetto. Per un progetto .NET Core o .NET Standard questa opzione è disponibile facendo clic con il tasto destro del mouse sul nodo **Dipendenze** del progetto in Esplora soluzioni.

    Verrà visualizzata la pagina **Servizi connessi** come illustrato nell'immagine seguente:

    ![Scheda Servizi connessi di Visual Studio per .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. Nella pagina **Servizi connessi** fare clic su **Microsoft WCF Web Service Reference Provider**. Verrà visualizzata la procedura guidata**Configura riferimento al servizio Web WCF**:

    ![Scheda Endpoint di servizio di Visual Studio per .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. Selezionare un servizio.

    3a. Nella procedura guidata **Configura riferimento al servizio Web WCF** sono disponibili diverse opzioni di ricerca dei servizi:

     * Per cercare i servizi definiti nella soluzione corrente, fare clic sul pulsante **Individua**.
     * Per cercare i servizi ospitati all'indirizzo specificato, immettere un URL del servizio nella casella **Indirizzo** e fare clic sul pulsante **Vai**.
     * Per selezionare un file WSDL contenente le informazioni sui metadati del servizio Web, fare clic sul pulsante **Sfoglia**.

    3b. Selezionare il servizio dall'elenco dei risultati della ricerca nella casella **Servizi**. Se necessario, immettere lo spazio dei nomi per il codice generato nella casella di testo **Spazio dei nomi** corrispondente.

    3c. Fare clic sul pulsante **Avanti** per aprire le pagine **Opzioni tipi di dati** e **Opzioni client**. In alternativa, fare clic sul pulsante **Fine** per usare le opzioni predefinite.

4. Il modulo **Opzioni tipi di dati** consente di ridefinire le impostazioni di configurazione del riferimento al servizio generato:

    ![Scheda Opzioni tipi di dati di Visual Studio per .NET Core](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

    > [!NOTE]
    > La casella di controllo **Riutilizza tipi in assembly di riferimento** è utile quando i tipi di dati necessari per la generazione del codice del riferimento al servizio sono definiti in uno degli assembly di riferimento del progetto.  È importante riusare tali tipi di dati esistenti per evitare problemi di runtime o conflitto del tipo in fase di compilazione.

    È possibile che si verifichi un ritardo durante il caricamento delle informazioni, a seconda del numero di dipendenze del progetto e di altri fattori relativi alle prestazioni di sistema. Il pulsante **Fine** è disabilitato durante il caricamento, a meno che la casella di controllo **Riutilizza tipi in assembly di riferimento** non sia selezionata.

5. Fare clic su **Fine** al termine dell'operazione.

Durante la visualizzazione dello stato, lo strumento:

- Scarica i metadati dal servizio WCF.
- Genera il codice del riferimento al servizio in un file denominato *reference.cs*e lo aggiunge al progetto sotto il nodo **Servizi connessi**.
- Aggiorna il file di progetto con estensione csproj con i riferimenti al pacchetto NuGet necessari per la compilazione e l'esecuzione nella piattaforma di destinazione.

![Finestra di stato di Visual Studio](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

Al termine di questi processi, è possibile creare un'istanza del tipo di client WCF generato e richiamare le operazioni del servizio.

## <a name="see-also"></a>Vedere anche

- [Introduzione alle applicazioni Windows Communication Foundation](../../framework/wcf/getting-started-tutorial.md)
- [Windows Communication Foundation services and WCF data services in Visual Studio](/visualstudio/data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio)
- [WCF supported features on .NET Core](https://github.com/dotnet/wcf/blob/master/release-notes/SupportedFeatures-v2.1.0.md)

## <a name="feedback--questions"></a>Commenti, suggerimenti e domande

Se hai domande o commenti, segnalalo alla [Community degli sviluppatori](https://developercommunity.visualstudio.com/) utilizzando lo strumento Segnala un [problema.](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)

## <a name="release-notes"></a>Note sulla versione

- Fare riferimento alle [note sulla versione](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) per informazioni aggiornate sulle versioni, compresi i problemi noti.
