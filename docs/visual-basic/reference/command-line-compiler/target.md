---
title: -target
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
ms.openlocfilehash: d186670489ada51fced67ff9adeb73b14909b664
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716693"
---
# <a name="-target-visual-basic"></a>-target (Visual Basic)

Specifica il formato dell'output del compilatore.

## <a name="syntax"></a>Sintassi

```console
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}
```

## <a name="remarks"></a>Note

Nella tabella seguente sono riepilogati gli effetti dell'opzione `-target`.

|**Opzione**|**Classe Behavior**|
|----------------|------------------|
|`-target:exe`|Determina la creazione di un'applicazione console eseguibile da parte del compilatore.<br /><br /> Questa è l'opzione predefinita se non è specificata alcuna opzione `-target`. Il file eseguibile viene creato con estensione exe.<br /><br /> Se non diversamente specificato con l'opzione `-out`, il nome del file di output prende il nome del file di input che contiene la procedura `Sub Main`.<br /><br /> Nei file del codice sorgente compilati in un file con estensione exe è necessaria una sola procedura `Sub Main`. Usare l'opzione del compilatore `-main` per specificare la classe che contiene la routine `Sub Main`.|
|`-target:library`|Determina la creazione di una libreria di collegamento dinamico (DLL) da parte del compilatore.<br /><br /> Il file della libreria a collegamento dinamico viene creato con estensione dll.<br /><br /> Se non diversamente specificato con l'opzione `-out`, il nome del file di output prende il nome del primo file di input.<br /><br /> Quando si compila una DLL, non è necessaria una procedura `Sub Main`.|
|`-target:module`|Fa in modo che il compilatore generi un modulo che può essere aggiunto a un assembly.<br /><br /> Il file di output viene creato con estensione. netmodule.<br /><br /> Il Common Language Runtime .NET non è in grado di caricare un file che non dispone di un assembly. Tuttavia, è possibile incorporare un file di questo tipo nel manifesto dell'assembly di un assembly utilizzando `-reference`.<br /><br /> Quando il codice in un modulo fa riferimento a tipi interni in un altro modulo, è necessario incorporare entrambi i moduli in un manifesto dell'assembly usando `-reference`.<br /><br /> L'opzione [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) importa i metadati da un modulo.|
|`-target:winexe`|Fa in modo che il compilatore crei un'applicazione eseguibile basata su Windows.<br /><br /> Il file eseguibile viene creato con estensione exe. Un'applicazione basata su Windows è una che fornisce un'interfaccia utente dalla libreria di classi .NET Framework o con le API di Windows.<br /><br /> Se non diversamente specificato con l'opzione `-out`, il nome del file di output prende il nome del file di input che contiene la procedura `Sub Main`.<br /><br /> Nei file del codice sorgente compilati in un file con estensione exe è necessaria una sola procedura `Sub Main`. Nei casi in cui il codice ha più di una classe con una procedura `Sub Main`, usare l'opzione del compilatore `-main` per specificare la classe che contiene la routine `Sub Main`|
|`-target:appcontainerexe`|Fa in modo che il compilatore crei un'applicazione basata su Windows eseguibile che deve essere eseguita in un contenitore di app. Questa impostazione è progettata per essere utilizzata per le applicazioni Windows 8. x Store.<br /><br /> L'impostazione **appcontainerexe** imposta un bit nel campo caratteristiche del file [eseguibile portatile](/windows/desktop/Debug/pe-format) . Questo bit indica che l'app deve essere eseguita in un contenitore di app. Quando questo bit è impostato, si verifica un errore se il metodo `CreateProcess` tenta di avviare l'applicazione all'esterno di un contenitore di app. A parte questa impostazione di bit, **-target: appcontainerexe** è equivalente a **-target: winexe**.<br /><br /> Il file eseguibile viene creato con estensione exe.<br /><br /> A meno che non si specifichi diversamente utilizzando l'opzione `-out`, il nome del file di output prende il nome del file di input che contiene la procedura `Sub Main`.<br /><br /> Nei file del codice sorgente compilati in un file con estensione exe è necessaria una sola procedura `Sub Main`. Se il codice contiene più di una classe con una procedura `Sub Main`, utilizzare l'opzione del compilatore `-main` per specificare la classe che contiene la routine `Sub Main`|
|`-target:winmdobj`|Fa in modo che il compilatore crei un file intermedio che è possibile convertire in un file binario Windows Runtime (WinMD). Il file con estensione winmd può essere utilizzato da JavaScript C++ e programmi, oltre ai programmi di linguaggio gestito.<br /><br /> Il file intermedio viene creato con estensione winmdobj.<br /><br /> A meno che non si specifichi diversamente utilizzando l'opzione `-out`, il nome del file di output assume il nome del primo file di input. Non è necessaria una procedura di `Sub Main`.<br /><br /> Il file con estensione winmdobj è progettato per essere utilizzato come input per lo strumento di esportazione <xref:Microsoft.Build.Tasks.WinMDExp> per produrre un file di metadati di Windows (WinMD). Il file WinMD ha un'estensione. winmd e contiene sia il codice della libreria originale che le definizioni WinMD usate da JavaScript, C++e dal Windows Runtime.|

A meno che non si specifichi `-target:module`, `-target` fa in modo che un manifesto dell'assembly .NET Framework venga aggiunto a un file di output.

Ogni istanza di vbc. exe produce al massimo un file di output. Se si specifica un'opzione del compilatore, ad esempio `-out` o `-target` più di una volta, viene applicato l'ultimo processo del compilatore. Le informazioni su tutti i file in una compilazione vengono aggiunte al manifesto. Tutti i file di output, ad eccezione di quelli creati con `-target:module` contengono metadati dell'assembly nel manifesto. Utilizzare [Ildasm. exe (DISASSEMBLER il)](../../../framework/tools/ildasm-exe-il-disassembler.md) per visualizzare i metadati in un file di output.

La forma breve di `-target` è `-t`.

### <a name="to-set--target-in-the-visual-studio-ide"></a>Per impostare-target nell'IDE di Visual Studio

1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.

2. Fare clic sulla scheda **Applicazione** .

3. Modificare il valore nella casella **tipo di applicazione** .

## <a name="example"></a>Esempio

Il codice seguente compila `in.vb`, creando `in.dll`:

```console
vbc -target:library in.vb
```

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)
- [Assembly in .NET](../../../standard/assembly/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
