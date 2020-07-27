---
title: Creare una libreria di classi di .NET Standard con Visual Studio
description: Informazioni su come creare una libreria di classi .NET Standard usando Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 69259b1d47a8e30945c578db10c6d697c81fa261
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164403"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio"></a>Esercitazione: creare una libreria di .NET Standard con Visual Studio

In questa esercitazione si creerà una semplice libreria di utilità contenente un solo metodo di gestione delle stringhe. Viene implementato come metodo di [estensione](../../csharp/programming-guide/classes-and-structs/extension-methods.md) in modo che sia possibile chiamarlo come se fosse un membro della <xref:System.String> classe.

La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione. Una libreria di classi destinata a .NET Standard 2,0 consente la chiamata della libreria da qualsiasi implementazione di .NET che supporti tale versione di .NET Standard. Una volta completata la libreria di classi, è possibile distribuirla come componente di terze parti o come componente in bundle con una o più applicazioni.

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019 versione 16,6 o una versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro **sviluppo multipiattaforma .NET Core** installato. .NET Core 3,1 SDK viene installato automaticamente quando si seleziona questo carico di lavoro.

  Per ulteriori informazioni, vedere la sezione [install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) nell'articolo [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) .

## <a name="create-a-solution"></a>Creare una soluzione

Iniziare creando una soluzione vuota in cui inserire il progetto libreria di classi. Una soluzione di Visual Studio funge da contenitore per uno o più progetti. Verranno aggiunti altri progetti correlati alla stessa soluzione.

Per creare la soluzione vuota:

1. Avviare Visual Studio.

2. Nella finestra Start scegliere **Crea un nuovo progetto**.

3. Nella pagina **Crea un nuovo progetto** immettere **soluzione** nella casella di ricerca. Scegliere il modello di **soluzione vuota** , quindi scegliere **Avanti**.

   ![Modello Soluzione vuota in Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. Nella pagina **Configura nuovo progetto** immettere **ClassLibraryProjects** nella casella **nome progetto** . Scegli quindi **Crea**.

## <a name="create-a-class-library-project"></a>Creare un progetto di libreria di classi

1. Aggiungere un nuovo progetto di libreria di classi .NET Standard denominato "StringLibrary" alla soluzione.

   1. Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliere **Aggiungi**  >  **nuovo progetto**.

   1. Nella pagina **Aggiungi nuovo progetto** immettere **Library** nella casella di ricerca. Scegliere **C#** o **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma. Scegliere il modello **libreria di classi (.NET standard)** , quindi fare clic su **Avanti**.

   1. Nella pagina **Configura nuovo progetto** immettere **StringLibrary** nella casella **nome progetto** . Quindi scegliere **Crea**.

1. Verificare che la libreria sia destinata alla versione corretta di .NET Standard. Fare clic con il pulsante destro del mouse sul progetto di libreria in **Esplora soluzioni**, quindi scegliere **Proprietà**. La casella di testo **Framework di destinazione** indica che il progetto è destinato a .NET standard 2,0.

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/library-project-properties.png)

1. Se si usa Visual Basic, cancellare il testo nella casella di testo **spazio dei nomi radice** .

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/vb/library-project-properties.png)

   Per ogni progetto Visual Basic crea automaticamente uno spazio dei nomi che corrisponde al nome del progetto. In questa esercitazione si definisce uno spazio dei nomi di primo livello usando la [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) parola chiave nel file di codice.

1. Sostituire il codice nella finestra del codice per *Class1.cs* o *Class1. vb* con il codice seguente e salvare il file. Se la lingua che si desidera utilizzare non è visualizzata, modificare il selettore della lingua nella parte superiore della pagina.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   La libreria di classi, `UtilityLibraries.StringLibrary` , contiene un metodo denominato `StartsWithUpper` . Questo metodo restituisce un <xref:System.Boolean> valore che indica se l'istanza di stringa corrente inizia con un carattere maiuscolo. Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli. Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.

1. Nella barra dei menu selezionare **Compila**  >  **Compila soluzione** per verificare che il progetto venga compilato senza errori.

## <a name="add-a-console-app-to-the-solution"></a>Aggiungere un'app console alla soluzione

Aggiungere un'applicazione console che usa la libreria di classi. L'app chiede all'utente di immettere una stringa e segnala se la stringa inizia con un carattere maiuscolo.

1. Aggiungere alla soluzione una nuova applicazione console .NET Core denominata "ShowCase".

   1. Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliere **Aggiungi**  >  **nuovo progetto**.

   1. Nella pagina **Aggiungi nuovo progetto** immettere **console** nella casella di ricerca. Scegliere **C#** o **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma.

   1. Scegliere il modello **app console (.NET Core)** , quindi fare clic su **Avanti**.

   1. Nella pagina **Configura nuovo progetto** immettere **Showcase** nella casella **nome progetto** . Scegli quindi **Crea**.

1. Nella finestra del codice per il file *Program.cs* o *Program. vb* sostituire tutto il codice con il codice seguente.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   Il codice usa la variabile `row` per mantenere il conteggio del numero di righe di dati scritti nella finestra della console. Ogni volta che è maggiore o uguale a 25, il codice Cancella la finestra della console e visualizza un messaggio all'utente.

   Il programma richiede all'utente di immettere una stringa. Indica se la stringa inizia con un carattere maiuscolo. Se l'utente preme il tasto <kbd>invio</kbd> senza immettere una stringa, l'applicazione termina e la finestra della console si chiude.

## <a name="add-a-project-reference"></a>Aggiungere un riferimento al progetto

Inizialmente, il nuovo progetto di app console non ha accesso alla libreria di classi. Per consentire la chiamata di metodi nella libreria di classi, creare un riferimento di progetto al progetto libreria di classi.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul `ShowCase` nodo **dipendenze** del progetto e scegliere **Aggiungi riferimento al progetto**.

   ![Menu di scelta rapida Aggiungi riferimento in Visual Studio](media/library-with-visual-studio/add-reference-context-menu.png)

1. Nella finestra di dialogo **Gestione riferimenti** selezionare il progetto **StringLibrary** e fare clic su **OK**.

   ![Finestra di dialogo Gestione riferimenti con StringLibrary selezionato](media/library-with-visual-studio/manage-project-references.png)

## <a name="run-the-app"></a>Eseguire l'app

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **ShowCase** e selezionare **Imposta come progetto di avvio** nel menu di scelta rapida.

   ![Menu di scelta rapida del progetto di Visual Studio per impostare il progetto di avvio](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. Premere <kbd>CTRL</kbd> + <kbd>F5</kbd> per compilare ed eseguire il programma senza debug.

   ![Barra degli strumenti del progetto di Visual Studio con il pulsante debug](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. Per provare il programma, immettere le stringhe e premere <kbd>invio</kbd>, quindi premere <kbd>invio</kbd> per uscire.

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Finestra della console con presentazione in esecuzione":::

## <a name="additional-resources"></a>Risorse aggiuntive

* [Sviluppare librerie con la interfaccia della riga di comando di .NET Core](libraries.md)
* [.NET standard le versioni e le piattaforme supportate](../../standard/net-standard.md).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata creata una soluzione, è stato aggiunto un progetto di libreria e è stato aggiunto un progetto di app console che usa la libreria. Nell'esercitazione successiva si aggiunge un progetto di unit test alla soluzione.

> [!div class="nextstepaction"]
> [Testare una libreria di .NET Standard con .NET Core con Visual Studio](testing-library-with-visual-studio.md)
