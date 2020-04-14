---
title: Sviluppo multipiattaforma con la libreria di classi portabile
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
ms.openlocfilehash: 7caddd7361b8f364762fb4357e35cb918ae99263
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242803"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a>Sviluppo multipiattaforma con la libreria di classi portabileCross-platform development with the Portable Class Library

Il tipo di progetto Libreria di classi portabile in Visual Studio consente di creare app e librerie multipiattaforma per piattaforme Microsoft in modo rapido e semplice.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

Le librerie di classi portabili consentono di ridurre il tempo e i costi di sviluppo e test del codice. Usare questo tipo di progetto per scrivere e compilare assembly .NET Framework portabili e quindi fare riferimento a tali assembly da app destinate a più piattaforme, ad esempio .NET Framework, iOS o Mac.Use this project type to write and build portable .NET Framework assemblies, and then reference those assemblies from apps that target multiple platforms such as the .NET Framework, iOS, or Mac.

Anche dopo aver creato un progetto Libreria di classi portabile in Visual Studio e aver iniziato lo sviluppo, è possibile modificare le piattaforme di destinazione. Visual Studio compila la libreria con i nuovi assembly, che consente di identificare le modifiche che è necessario apportare nel codice.

## <a name="create-a-portable-class-library-project"></a>Creare un progetto Libreria di classi portabileCreate a Portable Class Library project

Per creare una libreria di classi portabile, usare il modello fornito in Visual Studio.To create a Portable Class Library, use the template provided in Visual Studio. Creare un nuovo progetto (**File** > **nuovo progetto**) e nella finestra di dialogo Nuovo **progetto** selezionare il linguaggio di programmazione in uso (Visual C.NET o Visual Basic). Selezionare quindi il modello Libreria di classi **(legacy Portable).** Immettere un nome per il progetto e scegliere **OK**.

Verrà visualizzata la finestra di dialogo Aggiungi libreria di classi **portabile.** Scegliere due o più destinazioni, quindi scegliere **OK**.

![Aggiungere destinazioni della libreria di classi portabile in Visual StudioAdd portable class library targets in Visual Studio](media/add-portable-class-library.png)

## <a name="change-targets"></a>Modificare gli obiettivi

È possibile modificare le piattaforme di destinazione di un progetto di libreria di classi portabile quando lo si crea o dopo aver avviato lo sviluppo. Se si desidera modificare le destinazioni dopo aver creato il progetto, in **Esplora soluzioni**aprire il menu di scelta rapida per il progetto Libreria di classi portabile (non la soluzione), quindi scegliere **Proprietà**. Nella pagina delle proprietà del progetto, la scheda **Libreria** mostra le piattaforme attualmente di destinazione del progetto.

![Proprietà del progetto per la libreria di classi portabile in Visual StudioProject properties for Portable Class Library in Visual Studio](media/pcl-project-properties.png)

Per aggiungere o rimuovere destinazioni, scegliere il pulsante **Cambia,** quindi selezionare e deselezionare le caselle di controllo appropriate.

Quando si modificano le destinazioni, le API disponibili per lo sviluppo del progetto cambiano in base alla selezione. Visual Studio segnala gli avvisi e gli errori che possono verificarsi in seguito alla modifica delle destinazioni.

Se si desidera valutare la portabilità degli assembly prima di apportare modifiche in Visual Studio, è possibile utilizzare [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).

## <a name="supported-types-and-members"></a>Tipi e membri supportati

I tipi e i membri disponibili nei progetti Libreria di classi portabile sono limitati da diversi fattori di compatibilità:

- Devono essere condivisi tra le destinazioni selezionate.

- Devono comportarsi in modo analogo tra le destinazioni.

- Non devono essere candidati per la deprecazione.

- Devono essere utili in un ambiente portabile, specialmente quando i membri di supporto non lo sono.

Se un membro è supportato in Libreria di classi portabile e per le destinazioni selezionate, verrà visualizzato nel progetto in IntelliSense. Tenere presente, tuttavia, che un'API può essere supportata in Libreria di classi portabile, ma la possibilità di usarla dipende dalle destinazioni selezionate.

## <a name="api-differences-in-the-portable-class-library"></a>Differenze tra API in Libreria di classi portabile

Per rendere compatibili gli assembly Libreria di classi portabile su tutte le piattaforme supportate, alcuni membri sono stati leggermente modificati in Libreria di classi portabile.

## <a name="use-the-portable-class-library"></a>Utilizzare la libreria di classi portabileUse the Portable Class Library

Dopo avere compilato il progetto Libreria di classi portabile, è sufficiente farvi riferimento da altri progetti. È possibile fare riferimento al progetto o ad assembly specifici che contengono le classi a cui si desidera accedere.

Per eseguire un'app che faccia riferimento a un assembly Libreria di classi portabile, la versione richiesta (o successiva) delle piattaforme di destinazione deve essere installata nel computer. Visual Studio contiene tutti i framework richiesti, quindi è possibile eseguire l'app senza ulteriori modifiche nel computer usato per sviluppare l'app.

### <a name="deploy-a-universal-windows-app"></a>Distribuire un'app Windows universale

Quando crei un'app windows universale che fa riferimento a un assembly della libreria di classi portabile, tutto ciò che serve per distribuire l'app è incluso nel pacchetto dell'app e non sono necessari ulteriori passaggi.

### <a name="deploy-a-net-framework-app"></a>Distribuire un'app .NET Framework

Quando si distribuisce un'app .NET Framework che fa riferimento a un assembly Libreria di classi portabile, è necessario specificare una dipendenza dalla versione corretta di .NET Framework. Specificando questa dipendenza, ci si assicura che la versione richiesta per l'app sia installata.

- Per creare una dipendenza con la distribuzione ClickOnce: in **Esplora soluzioni**scegliere il nodo del progetto per il progetto da pubblicare. (Questo è il progetto che fa riferimento al progetto Libreria di classi portabile.) Sulla barra dei menu scegliere**Proprietà** **progetto** > , quindi scegliere la scheda **Pubblica.** Nella pagina **Pubblica** scegliere **Prerequisiti**. Selezionare la versione di .NET Framework richiesta come prerequisito.

- Per creare una dipendenza con un progetto di installazione: in **Esplora soluzioni**scegliere il progetto di installazione. Sulla barra dei menu scegliere**Prerequisiti****delle proprietà** >  **del progetto** > . Selezionare la versione di .NET Framework richiesta come prerequisito.

Per ulteriori informazioni sulla distribuzione di app .NET Framework, vedere [Guida alla distribuzione per gli sviluppatori.](../../../docs/framework/deployment/deployment-guide-for-developers.md)

## <a name="see-also"></a>Vedere anche

- [Utilizzo della libreria di classi portabile con MVVM](using-portable-class-library-with-model-view-view-model.md)
- [Risorse dell'app per librerie destinate a più piattaformeApp Resources for Libraries That Target Multiple Platforms](app-resources-for-libraries-that-target-multiple-platforms.md)
- [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [Supporto .NET Framework per applicazioni Windows Store e Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [Distribuzione](../../../docs/framework/deployment/net-framework-applications.md)
