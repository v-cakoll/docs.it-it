---
title: Compilazione di una libreria di classi .NET Standard in Visual Studio
description: Informazioni su come compilare una libreria di classi .NET Standard scritta C# in o Visual Basic con Visual Studio
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 748a1499e0c3a4a41613a69b715dbcfbd585bfe3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714013"
---
# <a name="build-a-net-standard-library-in-visual-studio"></a>Creare una libreria di .NET Standard in Visual Studio

La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione. Una libreria di classi destinata a .NET Standard 2,0 consente la chiamata della libreria da qualsiasi implementazione di .NET che supporti tale versione di .NET Standard. Dopo aver completato la libreria di classi, è possibile decidere se si vuole distribuirla come componente di terze parti o se si vuole includerla come componente in bundle con una o più applicazioni.

> [!NOTE]
> Per un elenco delle versioni di .NET Standard e delle piattaforme supportate, vedere [.NET standard](../../standard/net-standard.md).

In questo argomento si creerà una semplice libreria di utilità contenente un solo metodo di gestione delle stringhe, che verrà implementato come [metodo di estensione](../../csharp/programming-guide/classes-and-structs/extension-methods.md), in modo da poter essere chiamato come se fosse un membro della classe <xref:System.String>.

## <a name="create-a-visual-studio-solution"></a>Creare una soluzione di Visual Studio

Iniziare creando una soluzione vuota in cui inserire il progetto libreria di classi. Una soluzione di Visual Studio funge da contenitore per uno o più progetti. Se si continua con la serie di esercitazioni, verranno aggiunti altri progetti correlati alla stessa soluzione.

Per creare la soluzione vuota:

1. Apri Visual Studio.

2. Nella finestra iniziale scegliere **Crea un nuovo progetto**.

3. Nella pagina **Crea un nuovo progetto** immettere **soluzione** nella casella di ricerca. Scegliere il modello di **soluzione vuota** , quindi scegliere **Avanti**.

   ![Modello Soluzione vuota in Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. Nella pagina **Configura nuovo progetto** immettere **ClassLibraryProjects** nella casella **nome progetto** . Scegliere **Crea**.

> [!TIP]
> È anche possibile ignorare questo passaggio e consentire a Visual Studio di creare la soluzione quando si crea il progetto nel passaggio successivo. Cercare le opzioni della soluzione nella pagina **Configura nuovo progetto** .

## <a name="create-a-class-library-project"></a>Creare un progetto di libreria di classi

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

1. Aggiungere un nuovo C# progetto di libreria di classi .NET standard denominato "StringLibrary" alla soluzione.

   1. Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliere **Aggiungi** > **nuovo progetto**.

   1. Nella pagina **Aggiungi nuovo progetto** immettere **Library** nella casella di ricerca. Scegliere **C#** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma. Scegliere il modello **libreria di classi (.NET standard)** , quindi fare clic su **Avanti**.

   1. Nella pagina **Configura nuovo progetto** immettere **StringLibrary** nella casella **nome progetto** . Scegliere **Crea**.

1. Verificare che la libreria sia destinata alla versione corretta di .NET Standard. Fare clic con il pulsante destro del mouse sul progetto di libreria in **Esplora soluzioni**, quindi scegliere **Proprietà**. La casella di testo **Framework di destinazione** indica che il progetto è destinato a .NET standard 2,0.

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/library-project-properties.png)

1. Nella finestra del codice sostituire il codice con il seguente:

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   La libreria di classi, `UtilityLibraries.StringLibrary`, contiene un metodo denominato `StartsWithUpper`. Questo metodo restituisce un valore <xref:System.Boolean> che indica se l'istanza di stringa corrente inizia con un carattere maiuscolo. Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli. Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.

1. Nella barra dei menu selezionare **Compila** > **Compila soluzione**.

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

1. Aggiungere una nuova Visual Basic .NET Standard progetto libreria di classi denominato "StringLibrary" alla soluzione.

   1. Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliere **Aggiungi** > **nuovo progetto**.

   1. Nella pagina **Aggiungi nuovo progetto** immettere **Library** nella casella di ricerca. Scegliere **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma. Scegliere il modello **libreria di classi (.NET standard)** , quindi fare clic su **Avanti**.

   1. Nella pagina **Configura nuovo progetto** immettere **StringLibrary** nella casella **nome progetto** . Scegliere **Crea**.

1. Verificare che la libreria sia destinata alla versione corretta di .NET Standard. Fare clic con il pulsante destro del mouse sul progetto di libreria in **Esplora soluzioni**, quindi scegliere **Proprietà**. La casella di testo **Framework di destinazione** indica che il progetto è destinato a .NET standard 2,0.

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/vb/library-project-properties.png)

1. Nella finestra di dialogo **Proprietà** deselezionare il testo nella casella di testo **spazio dei nomi radice** . Per ogni progetto Visual Basic crea automaticamente uno spazio dei nomi che corrisponde al nome del progetto. In questa esercitazione si definisce uno spazio dei nomi di primo livello usando la parola chiave [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) nel file di codice.

1. Nella finestra del codice sostituire il codice con il seguente:

   [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   La libreria di classi, `UtilityLibraries.StringLibrary`, contiene un metodo denominato `StartsWithUpper`. Questo metodo restituisce un valore <xref:System.Boolean> che indica se l'istanza di stringa corrente inizia con un carattere maiuscolo. Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli. Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.

1. Nella barra dei menu selezionare **Compila** > **Compila soluzione**.

---

   Il progetto dovrebbe essere compilato senza errori.

## <a name="next-steps"></a>Passaggi successivi

La compilazione della libreria è stata completata. Non è tuttavia possibile sapere se funziona come previsto poiché non è stato ancora chiamato uno dei metodi. Il passaggio successivo per lo sviluppo della libreria consiste nel testarlo.

> [!div class="nextstepaction"]
> [Creare un progetto di unit test](testing-library-with-visual-studio.md)
