---
title: -target (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e3f691da48db863edd20bc6881785940a5451ef
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46524798"
---
# <a name="-target-visual-basic"></a>-target (Visual Basic)
Specifica il formato di output del compilatore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>Note  
 Nella tabella seguente sono riepilogati gli effetti del `-target` opzione.  
  
|**Opzione**|**Comportamento**|  
|----------------|------------------|  
|`-target:exe`|Indica al compilatore di creare un'applicazione console eseguibile.<br /><br /> Si tratta dell'opzione predefinita se non si specifica `-target` opzione specificata. Il file eseguibile viene creato con un'estensione .exe.<br /><br /> Se non diversamente specificato con il `/out` opzione, il nome del file di output accetta il nome del file di input che contiene il `Sub Main` procedure.<br /><br /> Un solo `Sub Main` procedura è necessaria nei file di codice sorgente compilati in un file .exe. Usare la `-main` opzione del compilatore per specificare la classe che contiene il `Sub Main` procedure.|  
|`-target:library`|Indica al compilatore di creare una libreria di collegamento dinamico (DLL).<br /><br /> Il file di libreria a collegamento dinamico viene creato con l'estensione dll.<br /><br /> Se non diversamente specificato con il `-out` opzione, il nome del file di output richiede il nome del primo file di input.<br /><br /> Quando si compila una DLL, un `Sub Main` procedura non è necessaria.|  
|`-target:module`|Indica al compilatore di generare un modulo che può essere aggiunto a un assembly.<br /><br /> Il file di output viene creato con un'estensione di file con estensione netmodule.<br /><br /> .NET common language runtime non è possibile caricare un file che non dispone di un assembly. Tuttavia, è possibile incorporare tali file nel manifesto dell'assembly di un assembly usando `-reference`.<br /><br /> Quando il codice di un modulo fa riferimento a tipi interni in un altro modulo, è necessario incorporare entrambi i moduli in un manifesto dell'assembly usando `-reference`.<br /><br /> Il [- addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opzione Importa i metadati da un modulo.|  
|`-target:winexe`|Indica al compilatore di creare un'applicazione eseguibile basato su Windows.<br /><br /> Il file eseguibile viene creato con un'estensione .exe. Un'applicazione basata su Windows è uno che fornisce un'interfaccia utente da una di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] libreria di classi o con le API Win32.<br /><br /> Se non diversamente specificato con il `-out` opzione, il nome del file di output accetta il nome del file di input che contiene il `Sub Main` procedure.<br /><br /> Un solo `Sub Main` procedura è necessaria nei file di codice sorgente compilati in un file .exe. Nei casi in cui il codice ha più di una classe che ha un `Sub Main` procedure, usare il `-main` opzione del compilatore per specificare la classe che contiene il `Sub Main` procedure|  
|`-target:appcontainerexe`|Indica al compilatore di creare un'applicazione basata su Windows eseguibile che deve essere eseguita in un contenitore di app. Questa impostazione è progettata per essere usato per [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] applicazioni.<br /><br /> Il **appcontainerexe** impostazione imposta un bit nel campo le caratteristiche delle [eseguibile portabile](/windows/desktop/Debug/pe-format) file. Questo bit indica che l'app deve essere eseguita in un contenitore di app. Quando questo bit viene impostato, si verifica un errore se il `CreateProcess` metodo tenta di avviare l'applicazione all'esterno di un contenitore di app. A prescindere da ciò bit impostato, **-target: appcontainerexe** equivale a **-target: winexe**.<br /><br /> Il file eseguibile viene creato con un'estensione .exe.<br /><br /> Se non diversamente specificato usando il `-out` opzione, il nome del file di output accetta il nome del file di input che contiene il `Sub Main` procedure.<br /><br /> Un solo `Sub Main` procedura è necessaria nei file di codice sorgente compilati in un file .exe. Se il codice contiene più di una classe che ha un `Sub Main` procedure, usare il `-main` opzione del compilatore per specificare la classe che contiene il `Sub Main` procedure|  
|`-target:winmdobj`|Indica al compilatore di creare un file intermedio che è possibile convertire in un file binario (con estensione winmd) di Windows Runtime. Il file. winmd può essere utilizzato dai programmi C++ e JavaScript, oltre ai programmi di linguaggi gestiti.<br /><br /> Viene creato il file intermedio con estensione winmdobj.<br /><br /> Se non diversamente specificato utilizzando il `-out` opzione, il nome del file di output richiede il nome del primo file di input. Oggetto `Sub Main` procedure non è obbligatorio.<br /><br /> Il file con estensione winmdobj è progettato per essere usato come input per il <xref:Microsoft.Build.Tasks.WinMDExp> dallo strumento per produrre un file di metadati (WinMD) di Windows di esportazione. Il file WinMD ha un'estensione. winmd e contiene il codice della libreria originale e le definizioni di WinMD da JavaScript, C++ e l'uso di Windows Runtime.|  
  
 Se non si specifica `-target:module`, `-target` causa un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] manifesto dell'assembly da aggiungere a un file di output.  
  
 Ogni istanza di Vbc.exe produce, al massimo un file di output. Se si specifica un'opzione del compilatore, ad esempio `-out` o `-target` più di una volta, quella più recente viene reso effettivo il compilatore elabora. Informazioni su tutti i file in una compilazione viene aggiunto al manifesto. Tutti i file tranne quelli creati con output `-target:module` contengono i metadati dell'assembly nel manifesto. Uso [Ildasm.exe (Disassembler IL)](../../../framework/tools/ildasm-exe-il-disassembler.md) per visualizzare i metadati in un file di output.  
  
 La forma breve di `-target` è `-t`.  
  
### <a name="to-set--target-in-the-visual-studio-ide"></a>Per impostare - destinazione nell'IDE di Visual Studio  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.   
  
2.  Fare clic sulla scheda **Applicazione** .  
  
3.  Modificare il valore di **tipo di applicazione** casella.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `in.vb`creando `in.dll`:  
  
```console
vbc -target:library in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)  
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
- [-riferimenti (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
- [-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)  
- [Assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
