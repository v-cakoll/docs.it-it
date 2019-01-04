---
title: Compilazione di una libreria di classi .NET Core con Visual Basic in Visual Studio 2017
description: Informazioni su come compilare una libreria di classi .NET Core scritta in Visual Basic usando Visual Studio 2017
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
dev_langs:
- vb
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 04d866c0615d299fe3df72553bafce2514a1c121
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168832"
---
# <a name="build-a-class-library-with-visual-basic-and-the-net-core-sdk-in-visual-studio-2017"></a>Compilare una libreria di classi con Visual Basic e .NET Core SDK in Visual Studio 2017

La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione. Una libreria di classi che esegue la destinazione a .NET Standard 2.0 consente la chiamata alla libreria da qualsiasi implementazione di .NET che supporti questa versione di .NET Standard. Dopo aver completato la libreria di classi, è possibile decidere se si vuole distribuirla come componente di terze parti o se si vuole includerla come componente in bundle con una o più applicazioni.

> [!NOTE]
> Per un elenco delle versioni di .NET Standard e delle piattaforme supportate, vedere [.NET Standard](../../standard/net-standard.md).

In questo argomento si creerà una semplice libreria di utilità contenente un solo metodo di gestione delle stringhe, che verrà implementato come [metodo di estensione](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md), in modo da poter essere chiamato come se fosse un membro della classe <xref:System.String>.

## <a name="creating-a-class-library-solution"></a>Creazione di una soluzione per la libreria di classi

Iniziare creando una soluzione per il progetto di libreria di classi e per i progetti correlati. Una soluzione Visual Studio funge solo da contenitore per uno o più progetti. Per creare la soluzione:

1. Nella barra dei menu di Visual Studio scegliere **File** > **Nuovo** > **Progetto**.

1. Nella finestra di dialogo **Nuovo progetto** espandere il nodo **Altri tipi di progetti** e selezionare **Soluzioni di Visual Studio**. Assegnare alla soluzione il nome "ClassLibraryProjects" e selezionare il pulsante **OK**.

   ![Finestra di dialogo per la creazione di un nuovo progetto di test in Visual Studio](./media/library-with-visual-studio/new-project-dialog.png)

## <a name="creating-the-class-library-project"></a>Creazione del progetto di libreria di classi

Creare un progetto di libreria di classi:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file della soluzione **ClassLibraryProjects** e dal menu di scelta rapida selezionare **Aggiungi** > **Nuovo progetto**.

1. Nella finestra di dialogo **Aggiungi nuovo progetto** espandere il nodo **Visual Basic**, quindi selezionare il nodo **.NET Standard** seguito dal modello di progetto **Libreria di classi (.NET Standard)**. Nella casella di testo **Nome** immettere "StringLibrary" come nome del progetto. Scegliere **OK** per creare il progetto di libreria di classi.

   ![Finestra di dialogo per l'aggiunta di un nuovo progetto di libreria di classi in Visual Studio](./media/vb-library-with-visual-studio/create-new-library-project.png)

   La finestra di codice viene quindi aperta nell'ambiente di sviluppo di Visual Studio. 
 
   ![Finestra dell'applicazione di Visual Studio che illustra il codice del modello della libreria di classi predefinito](./media/vb-library-with-visual-studio/visual-studio-library.png)

1. Assicurarsi che sia stata eseguita la destinazione della libreria alla versione corretta di .NET Standard. Fare clic con il pulsante destro del mouse sul progetto libreria nelle finestre di **Esplora soluzioni**, quindi selezionare **Proprietà**. La casella di testo **Framework di destinazione** indica che si sta eseguendo la destinazione a .NET 2.0 Standard.

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/library-project-properties.png)

1. Inoltre, nella finestra di dialogo **Proprietà** cancellare il testo nella casella di testo **Spazio dei nomi radice**. Per ogni progetto, Visual Basic crea automaticamente uno spazio dei nomi che corrisponde al nome del progetto e gli spazi dei nomi definiti nel file di codice sorgente sono gli elementi padre di questo spazio dei nomi. Si desidera definire uno spazio dei nomi di livello superiore usando la parola chiave [`namespace` ](../../visual-basic/language-reference/statements/namespace-statement.md).
  
1. Nella finestra del codice sostituire il codice con il seguente:

  [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   La libreria di classi `UtilityLibraries.StringLibrary` contiene un metodo denominato `StartsWithUpper`, che restituisce un valore <xref:System.Boolean> che indica se l'istanza della stringa corrente inizia con un carattere maiuscolo. Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli. Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.

1. Nella barra dei menu selezionare **Compila** > **Compila soluzione**. Il progetto dovrebbe essere compilato senza errori.

   ![Riquadro di output che illustra che la compilazione ha avuto esito positivo](./media/library-with-visual-studio/output-pane-successful-build.png)



## <a name="next-step"></a>Passaggio successivo

La compilazione della libreria è stata completata. Non è tuttavia possibile sapere se funziona come previsto poiché non è stato ancora chiamato uno dei metodi. Il passaggio successivo per lo sviluppo della libreria consiste nel testarla usando un [Progetto unit test](testing-library-with-visual-studio.md).
