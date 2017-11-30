---
title: /netcf
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a75573b0881af71e907a488c2b3c15db3816fc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="netcf"></a>/netcf
Imposta il compilatore in modo che punti a [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
/netcf  
```  
  
## <a name="remarks"></a>Note  
 Il `/netcf` opzione cause di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore di destinazione di [!INCLUDE[Compact](~/includes/compact-md.md)] anziché la versione completa [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Funzionalità di linguaggio che è presente solo nella versione completa [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] è disabilitato.  
  
 Il `/netcf` opzione è progettata per essere utilizzato con [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Le funzionalità del linguaggio per disabilitato `/netcf` sono le stesse funzionalità di linguaggio non presente nel file di destinazione con `/sdkpath`.  
  
> [!NOTE]
>  Il `/netcf` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando. Il `/netcf` opzione viene impostata quando un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] viene caricato il progetto di dispositivo.  
  
 Il `/netcf` opzione consente di modificare le funzionalità del linguaggio seguenti:  
  
-   Il [fine \<parola chiave > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) (parola chiave), che termina l'esecuzione di un programma, è disabilitato. Il seguente programma compilato ed eseguito senza `/netcf` ma non riesce in fase di compilazione con `/netcf`.  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   L'associazione tardiva, in tutti i form, è disabilitata. Quando si verificano gli scenari di associazione tardiva riconosciuti, vengono generati errori di compilazione. Il seguente programma compilato ed eseguito senza `/netcf` ma non riesce in fase di compilazione con `/netcf`.  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   Il [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), e [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modificatori sono disabilitati. La sintassi del [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) istruzione viene modificata anche a `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. Il codice seguente viene illustrato l'effetto di `/netcf` su una compilazione.  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   Utilizzo delle parole chiave di Visual Basic 6.0 che sono stati rimossi da [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] genera un errore diverso quando `/netcf` viene utilizzato. Questo riguarda i messaggi di errore per le parole chiave seguenti:  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `Myfile.vb` con il [!INCLUDE[Compact](~/includes/compact-md.md)], usando le versioni dei file mscorlib.dll e Microsoft.VisualBasic.dll trovato nella directory di installazione predefinita di [!INCLUDE[Compact](~/includes/compact-md.md)] nell'unità C. In genere, si utilizzerà la versione più recente di [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
