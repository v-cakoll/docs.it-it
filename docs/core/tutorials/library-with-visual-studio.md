---
title: Creare una libreria di classi .NET Standard in Visual StudioBuild a .NET Standard class library in Visual Studio
description: Informazioni su come compilare una libreria di classi .NET Standard scritta in Visual Basic o in Visual Basic utilizzando Visual Studio
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 748a1499e0c3a4a41613a69b715dbcfbd585bfe3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714013"
---
# <a name="build-a-net-standard-library-in-visual-studio"></a>Creare una libreria .NET Standard in Visual StudioBuild a .NET Standard library in Visual Studio

La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione. Una libreria di classi destinata a .NET Standard 2.0 consente di chiamare la libreria da qualsiasi implementazione di .NET che supporta tale versione di .NET Standard. Dopo aver completato la libreria di classi, è possibile decidere se si vuole distribuirla come componente di terze parti o se si vuole includerla come componente in bundle con una o più applicazioni.

> [!NOTE]
> Per un elenco delle versioni di .NET Standard e delle piattaforme supportate, vedere [.NET Standard](../../standard/net-standard.md).

In questo argomento si creerà una semplice libreria di utilità contenente un solo metodo di gestione delle stringhe, che verrà implementato come [metodo di estensione](../../csharp/programming-guide/classes-and-structs/extension-methods.md), in modo da poter essere chiamato come se fosse un membro della classe <xref:System.String>.

## <a name="create-a-visual-studio-solution"></a>Creare una soluzione di Visual StudioCreate a Visual Studio solution

Iniziare creando una soluzione vuota per inserire il progetto di libreria di classi in. Una soluzione di Visual Studio funge da contenitore per uno o più progetti. Si aggiungeranno altri progetti correlati alla stessa soluzione se si continua con la serie di esercitazioni.

Per creare la soluzione vuota:

1. Aprire Visual Studio.

2. Nella finestra di avvio scegliere **Crea un nuovo progetto.**

3. Nella pagina **Crea un nuovo progetto** immettere la **soluzione** nella casella di ricerca. Scegliere il modello **Soluzione vuota** e quindi **Avanti**.

   ![Modello Soluzione vuota in Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. Nella pagina **Configura il nuovo progetto** immettere **ClassLibraryProjects** nella casella **Nome progetto.** Scegliere quindi **Crea,** quindi Crea .

> [!TIP]
> È anche possibile ignorare questo passaggio e consentire a Visual Studio di creare automaticamente la soluzione quando si crea il progetto nel passaggio successivo. Cercare le opzioni della soluzione nella pagina **Configura il nuovo progetto.**

## <a name="create-a-class-library-project"></a>Creare un progetto di libreria di classi

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C #](#tab/csharp)

1. Aggiungere alla soluzione un nuovo progetto di libreria di classi .NET Standard di C.NET denominato "StringLibrary".

   1. Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e selezionare **Aggiungi** > **nuovo progetto**.

   1. Nella pagina **Aggiungi un nuovo progetto** immettere la **raccolta** nella casella di ricerca. Scegliere **C 'c'è** dall'elenco linguaggio e quindi scegliere **Tutte le piattaforme** dall'elenco piattaforma . Scegliere il modello Libreria di classi **(.NET Standard)** e quindi scegliere **Avanti**.

   1. Nella pagina **Configura il nuovo progetto** immettere **StringLibrary** nella casella **Nome progetto.** Scegliere quindi **Crea,** quindi Crea .

1. Verificare che la libreria sia destinata alla versione corretta di .NET Standard. Fare clic con il pulsante destro del mouse sul progetto di libreria in **Esplora soluzioni**, quindi scegliere **Proprietà**. La casella di testo Framework di destinazione indica che il progetto è destinato a .NET Standard 2.0.The **Target Framework** text box shows that the project targets .NET Standard 2.0.

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/library-project-properties.png)

1. Nella finestra del codice sostituire il codice con il seguente:

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   La libreria `UtilityLibraries.StringLibrary`di classi , `StartsWithUpper`, contiene un metodo denominato . Questo metodo <xref:System.Boolean> restituisce un valore che indica se l'istanza della stringa corrente inizia con un carattere maiuscolo. Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli. Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.

1. Nella barra dei menu selezionare **Compila** > **soluzione**.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Aggiungere alla soluzione un nuovo progetto di libreria di classi Visual Basic .NET Standard denominato "StringLibrary".

   1. Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e selezionare **Aggiungi** > **nuovo progetto**.

   1. Nella pagina **Aggiungi un nuovo progetto** immettere la **raccolta** nella casella di ricerca. Scegliere **Visual Basic** dall'elenco Linguaggio, quindi scegliere Tutte le **piattaforme** dall'elenco Piattaforma. Scegliere il modello Libreria di classi **(.NET Standard)** e quindi scegliere **Avanti**.

   1. Nella pagina **Configura il nuovo progetto** immettere **StringLibrary** nella casella **Nome progetto.** Scegliere quindi **Crea,** quindi Crea .

1. Verificare che la libreria sia destinata alla versione corretta di .NET Standard. Fare clic con il pulsante destro del mouse sul progetto di libreria in **Esplora soluzioni**, quindi scegliere **Proprietà**. La casella di testo Framework di destinazione indica che il progetto è destinato a .NET Standard 2.0.The **Target Framework** text box shows that the project targets .NET Standard 2.0.

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/vb/library-project-properties.png)

1. Nella finestra di dialogo **Proprietà** cancellare il testo nella casella di testo **Spazio dei nomi radice.** Per ogni progetto, Visual Basic crea automaticamente uno spazio dei nomi che corrisponde al nome del progetto. In questa esercitazione si definisce uno [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) spazio dei nomi di primo livello usando la parola chiave nel file di codice.

1. Nella finestra del codice sostituire il codice con il seguente:

   [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   La libreria `UtilityLibraries.StringLibrary`di classi , `StartsWithUpper`, contiene un metodo denominato . Questo metodo <xref:System.Boolean> restituisce un valore che indica se l'istanza della stringa corrente inizia con un carattere maiuscolo. Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli. Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.

1. Nella barra dei menu selezionare **Compila** > **soluzione**.

---

   Il progetto dovrebbe essere compilato senza errori.

## <a name="next-steps"></a>Passaggi successivi

La compilazione della libreria è stata completata. Non è tuttavia possibile sapere se funziona come previsto poiché non è stato ancora chiamato uno dei metodi. Il passaggio successivo nello sviluppo della libreria consiste nel testarla.

> [!div class="nextstepaction"]
> [Creare un progetto di unit test](testing-library-with-visual-studio.md)
