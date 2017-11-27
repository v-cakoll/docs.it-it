---
title: /target (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a8a9fcd6fa6dfaace01f8fbb7fa407145acc16f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="target-visual-basic"></a>/target (Visual Basic)
Specifica il formato dell'output del compilatore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>Note  
 Nella tabella seguente sono riepilogati gli effetti del `/target` opzione.  
  
|**Opzione**|**Comportamento**|  
|----------------|------------------|  
|`/target:exe`|Indica al compilatore di creare un'applicazione console eseguibile.<br /><br /> Si tratta dell'opzione predefinita se non si `/target` opzione specificata. Il file eseguibile viene creato con un'estensione .exe.<br /><br /> Se non diversamente specificato con il `/out` opzione, il nome del file di output accetta il nome del file di input che contiene il `Sub Main` stored procedure.<br /><br /> Un solo `Sub Main` procedura è necessario nei file di codice sorgente che vengono compilati in un file .exe. Utilizzare il `/main` l'opzione del compilatore per specificare la classe che contiene il `Sub Main` stored procedure.|  
|`/target:library`|Indica al compilatore di creare una libreria di collegamento dinamico (DLL).<br /><br /> Il file di libreria a collegamento dinamico viene creato con estensione dll.<br /><br /> Se non diversamente specificato con il `/out` opzione, il nome del file di output accetta il nome del primo file di input.<br /><br /> Quando si compila una DLL, un `Sub Main` procedura non è necessaria.|  
|`/target:module`|Determina la generazione di un modulo che può essere aggiunto a un assembly.<br /><br /> Il file di output viene creato con estensione netmodule.<br /><br /> .NET common language runtime non è possibile caricare un file che non dispone di un assembly. Tuttavia, è possibile incorporare tali file nel manifesto dell'assembly di un assembly utilizzando `/reference`.<br /><br /> Quando il codice in un modulo fa riferimento a tipi interni in un altro modulo, è necessario incorporare entrambi i moduli in un manifesto dell'assembly utilizzando `/reference`.<br /><br /> Il [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opzione Importa metadati da un modulo.|  
|`/target:winexe`|Indica al compilatore di creare un'applicazione eseguibile basato su Windows.<br /><br /> Il file eseguibile viene creato con un'estensione .exe. Un'applicazione basata su Windows è uno che fornisce un'interfaccia utente da uno di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] libreria di classi o le API Win32.<br /><br /> Se non diversamente specificato con il `/out` opzione, il nome del file di output accetta il nome del file di input che contiene il `Sub Main` stored procedure.<br /><br /> Un solo `Sub Main` procedura è necessario nei file di codice sorgente che vengono compilati in un file .exe. Nei casi in cui il codice ha più di una classe che ha un `Sub Main` procedure, utilizzare il `/main` l'opzione del compilatore per specificare la classe che contiene il `Sub Main` procedure|  
|`/target:appcontainerexe`|Indica al compilatore di creare un'applicazione eseguibile basato su Windows che deve essere eseguita in un contenitore di app. Questa impostazione è progettata per essere utilizzata per [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] applicazioni.<br /><br /> Il **appcontainerexe** impostazione imposta un bit nel campo di caratteristiche di [eseguibile](http://go.microsoft.com/fwlink/p/?LinkId=236960) file. Questo bit indica che è necessario eseguire l'app in un contenitore di app. Quando questo bit viene impostato, si verifica un errore se il `CreateProcess` metodo tenta di avviare l'applicazione all'esterno di un contenitore di app. A parte di questa impostazione, bit **/target: appcontainerexe** equivale a **/target: winexe**.<br /><br /> Il file eseguibile viene creato con un'estensione .exe.<br /><br /> Se non diversamente specificato utilizzando il `/out` opzione, il nome del file di output accetta il nome del file di input che contiene il `Sub Main` stored procedure.<br /><br /> Un solo `Sub Main` procedura è necessario nei file di codice sorgente che vengono compilati in un file .exe. Se il codice contiene più di una classe che ha un `Sub Main` procedure, utilizzare il `/main` l'opzione del compilatore per specificare la classe che contiene il `Sub Main` procedure|  
|`/target:winmdobj`|Indica al compilatore di creare un file intermedio che è possibile convertire in un file binario (con estensione winmd) di Windows Runtime. Il file con estensione winmd può essere utilizzato da programmi C++ e JavaScript, oltre ai programmi di linguaggi gestiti.<br /><br /> Il file intermedio viene creato con un'estensione con estensione winmdobj.<br /><br /> Se non diversamente specificato utilizzando il `/out` opzione, il nome del file di output accetta il nome del primo file di input. Oggetto `Sub Main` procedura non è necessario.<br /><br /> Il file con estensione winmdobj è progettato per essere utilizzato come input per il <xref:Microsoft.Build.Tasks.WinMDExp> esportare strumento per generare un file di metadati (WinMD) di Windows. Il file WinMD con estensione winmd e contiene sia il codice di libreria originale e le definizioni di WinMD che JavaScript, C++ e l'utilizzo di Windows Runtime.|  
  
 Se non si specifica `/target:module`, `/target` provoca un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] manifesto dell'assembly da aggiungere a un file di output.  
  
 Ogni istanza di Vbc.exe genera, al massimo un file di output. Se si specifica un'opzione del compilatore, ad esempio `/out` o `/target` più di una volta, l'ultima i processi del compilatore viene inserito in vigore. Informazioni su tutti i file in una compilazione viene aggiunto al manifesto. Tutti i file ad eccezione di quelli creati con output `/target:module` contengono i metadati dell'assembly nel manifesto. Utilizzare [Ildasm.exe (Disassembler IL)](https://msdn.microsoft.com/library/f7dy01k1) per visualizzare i metadati in un file di output.  
  
 La forma breve di `/target` è `/t`.  
  
### <a name="to-set-target-in-the-visual-studio-ide"></a>Per impostare /target nell'IDE di Visual Studio  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Fare clic sulla scheda **Applicazione** .  
  
3.  Modificare il valore di **tipo di applicazione** casella.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `in.vb`, creando `in.dll`:  
  
```  
vbc /target:library in.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [/out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [/moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)  
 [Assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
