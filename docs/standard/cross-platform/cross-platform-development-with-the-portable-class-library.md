---
title: Sviluppo multipiattaforma con la libreria di classi portabile
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
author: mairaw
ms.author: mairaw
ms.openlocfilehash: afaa8e118bb21e5c1e4f1c53b1d0d29ca6bb3bf5
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532076"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a>Sviluppo multipiattaforma con la libreria di classi portabile

Il tipo di progetto libreria di classi portabile in Visual Studio consente di compilare App multipiattaforma e librerie per piattaforme Microsoft, semplice e rapido.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

Le librerie di classi portabili consentono di ridurre il tempo e i costi di sviluppo e test del codice. Usare questo tipo di progetto per scrivere e compilare assembly .NET Framework portabili e farvi riferimento dalle App destinate a più piattaforme, ad esempio il Framework .NET, iOS o Mac.

Anche dopo aver creato un progetto Libreria di classi portabile in Visual Studio e aver iniziato lo sviluppo, è possibile modificare le piattaforme di destinazione. Visual Studio compila la libreria con i nuovi assembly, che consente di identificare le modifiche da apportare al codice.

## <a name="create-a-portable-class-library-project"></a>Creare un progetto libreria di classi portabile

Per creare una libreria di classi portabile, usare il modello fornito in Visual Studio. Creare un nuovo progetto (**File** > **nuovo progetto**) e la **nuovo progetto** finestra di dialogo, selezionare il linguaggio di programmazione (Visual c# o Visual Basic). Selezionare quindi il **libreria di classi (portabile Legacy)** modello. Immettere un nome per il progetto e scegliere **OK**.

Il **Aggiungi libreria di classi portabile** verrà visualizzata la finestra di dialogo. Scegliere due o più destinazioni e quindi scegliere **OK**.

![Aggiungere le destinazioni libreria di classi portabile in Visual Studio](media/add-portable-class-library.png)

## <a name="change-targets"></a>Modificare le destinazioni

Durante la creazione o dopo aver iniziato lo sviluppo, è possibile modificare le piattaforme di destinazione di un progetto di libreria di classi portabile. Se si desidera modificare le destinazioni dopo aver creato il progetto, in **Esplora soluzioni**, aprire il menu di scelta rapida per il progetto di libreria di classi portabile (non sulla soluzione) e quindi scegliere **proprietà** . Nella pagina delle proprietà del progetto, il **libreria** scheda Mostra le piattaforme di destinazione del progetto attualmente.

![Proprietà del progetto per la libreria di classi portabile in Visual Studio](media/pcl-project-properties.png)

Per aggiungere o rimuovere destinazioni, scegliere il **modifica** pulsante, quindi selezionare e deselezionare le caselle di controllo appropriate.

Quando si modificano le destinazioni, le API disponibili per lo sviluppo del progetto cambiano in base alla selezione. Visual Studio segnala gli avvisi e gli errori che possono verificarsi in seguito alla modifica delle destinazioni.

Se si vuole valutare la portabilità degli assembly prima di apportare modifiche in Visual Studio, è possibile usare la [.NET Portability Analyzer](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b).

## <a name="supported-types-and-members"></a>Tipi e membri supportati

I tipi e i membri disponibili nei progetti Libreria di classi portabile sono limitati da diversi fattori di compatibilità:

-   Devono essere condivisi tra le destinazioni selezionate.

-   Devono comportarsi in modo analogo tra le destinazioni.

-   Non devono essere candidati per la deprecazione.

-   Devono essere utili in un ambiente portabile, specialmente quando i membri di supporto non lo sono.

Se un membro è supportato in Libreria di classi portabile e per le destinazioni selezionate, verrà visualizzato nel progetto in IntelliSense. Tenere presente, tuttavia, che un'API può essere supportata in Libreria di classi portabile, ma la possibilità di usarla dipende dalle destinazioni selezionate.

## <a name="api-differences-in-the-portable-class-library"></a>Differenze tra API in Libreria di classi portabile

Per rendere compatibili gli assembly Libreria di classi portabile su tutte le piattaforme supportate, alcuni membri sono stati leggermente modificati in Libreria di classi portabile.

## <a name="use-the-portable-class-library"></a>Usare la libreria di classi portabile

Dopo avere compilato il progetto Libreria di classi portabile, è sufficiente farvi riferimento da altri progetti. È possibile fare riferimento al progetto o ad assembly specifici che contengono le classi a cui si desidera accedere.

Per eseguire un'app che faccia riferimento a un assembly Libreria di classi portabile, la versione richiesta (o successiva) delle piattaforme di destinazione deve essere installata nel computer. Visual Studio contiene tutti i framework richiesti, quindi è possibile eseguire l'app senza ulteriori modifiche nel computer usato per sviluppare l'app.

### <a name="deploy-a-universal-windows-app"></a>Distribuire un'app Windows universali

Quando si crea un'app Windows universali che fa riferimento a un assembly libreria di classi portabile, tutto il che necessario per distribuire l'app è inclusa nel pacchetto dell'app e non sono altri passaggi necessari.

### <a name="deploy-a-net-framework-app"></a>Distribuire .NET Framework app

Quando si distribuisce un'app .NET Framework che fa riferimento a un assembly Libreria di classi portabile, è necessario specificare una dipendenza dalla versione corretta di .NET Framework. Specificando questa dipendenza, ci si assicura che la versione richiesta per l'app sia installata.

-   Per creare una dipendenza con la distribuzione ClickOnce: In **Esplora soluzioni**, scegliere il nodo del progetto per il progetto da pubblicare. (Si tratta del progetto che fa riferimento al progetto Libreria di classi portabile.) Nella barra dei menu, scegliere **Project** > **delle proprietà**e quindi scegliere il **pubblica** scheda. Nel **Publish** pagina, scegliere **prerequisiti**. Selezionare la versione di .NET Framework richiesta come prerequisito.

-   Per creare una dipendenza con un progetto di installazione: nelle **Esplora soluzioni**, scegliere il progetto di installazione. Nella barra dei menu, scegliere **Project** > **delle proprietà** > **prerequisiti**. Selezionare la versione di .NET Framework richiesta come prerequisito.

Per altre informazioni sulla distribuzione di App .NET Framework, vedere [Guida alla distribuzione per gli sviluppatori](../../../docs/framework/deployment/deployment-guide-for-developers.md).

## <a name="see-also"></a>Vedere anche

- [Uso della libreria di classi portabile con MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md)
- [Risorse app per librerie destinate a più piattaforme](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md)
- [.NET portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)
- [Distribuzione](../../../docs/framework/deployment/net-framework-applications.md)
