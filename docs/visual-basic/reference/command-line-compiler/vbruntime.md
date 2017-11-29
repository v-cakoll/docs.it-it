---
title: /vbruntime
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dda8ea7285a748bac53e30af8bd7a60099fe7411
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="vbruntime"></a>/vbruntime
Indica che il compilatore deve compilare senza un riferimento alla libreria di runtime di Visual Basic oppure con un riferimento a una libreria di runtime specifica.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Argomenti  
 \-  
 Compilare senza un riferimento alla libreria di Runtime di Visual Basic.  
  
 \+  
 Compilare con un riferimento per il valore predefinito della libreria di Runtime di Visual Basic.  
  
 \*  
 Compilare senza un riferimento alla libreria di Runtime di Visual Basic e incorporare la funzionalità di base dalla libreria di Runtime di Visual Basic nell'assembly.  
  
 `path`  
 Compilare con un riferimento alla libreria (DLL) specificata.  
  
## <a name="remarks"></a>Note  
 Il `/vbruntime` l'opzione del compilatore consente di specificare che il compilatore deve compilare senza un riferimento alla libreria di Runtime di Visual Basic. Se esegue la compilazione senza un riferimento alla libreria di Runtime di Visual Basic, vengono registrati errori o avvisi in costrutti di linguaggio o codice che generano una chiamata a un supporto di runtime di Visual Basic. (A *helper di runtime di Visual Basic* è una funzione definita in Microsoft.VisualBasic.dll che viene chiamato in fase di esecuzione per eseguire una semantica del linguaggio specifica.)  
  
 Il `/vbruntime+` opzione produce lo stesso comportamento che si verifica quando non `/vbruntime` viene specificata l'opzione. È possibile utilizzare il `/vbruntime+` opzione per eseguire l'override precedente `/vbruntime` commutatori.  
  
 La maggior parte degli oggetti del `My` tipo non sono disponibili quando si utilizza il `/vbruntime-` o `vbruntime:``path` opzioni.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Incorporamento di funzionalità di base di Runtime di Visual Basic  
 Il `/vbruntime*` opzione consente di compilare senza un riferimento a una libreria di runtime. Al contrario, le funzionalità di base dalla libreria di Runtime di Visual Basic sono incorporata nell'assembly utente. È possibile utilizzare questa opzione se l'applicazione viene eseguita su piattaforme che non contengono il runtime di Visual Basic.  
  
 I seguenti membri di runtime vengono incorporati:  
  
-   Classe <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   Metodo <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   Metodo <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   Metodo <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack>(costante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr>(costante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf>(costante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed>(costante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf>(costante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine>(costante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar>(costante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString>(costante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab>(costante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>(costante)  
  
-   Alcuni oggetti del `My` tipo  
  
 Se si esegue la compilazione utilizzando il `/vbruntime*` opzione e il codice fa riferimento a un membro dalla libreria di Runtime di Visual Basic che non sono incorporati con le funzionalità di base, il compilatore restituisce un errore che indica che il membro non è disponibile.  
  
## <a name="referencing-a-specified-library"></a>Riferimento a una libreria specificata  
 È possibile utilizzare il `path` argomento per la compilazione con un riferimento a una libreria di runtime personalizzato anziché il valore predefinito della libreria di Runtime di Visual Basic.  
  
 Se il valore per il `path` argomento è un percorso completo di una DLL, il compilatore utilizza il file come libreria di runtime. Se il valore per il `path` argomento non è un percorso completo di una DLL, il compilatore Visual Basic eseguirà la ricerca prima di tutto per la DLL identificata nella cartella corrente. Quindi cercherà nel percorso specificato utilizzando il [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) l'opzione del compilatore. Se il `/sdkpath` l'opzione del compilatore non viene utilizzato, il compilatore eseguirà la ricerca per la DLL identificata nella cartella di .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il `/vbruntime` opzione per la compilazione con un riferimento a una raccolta personalizzata.  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Componenti di base di Visual Basic-nuova modalità di compilazione in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
