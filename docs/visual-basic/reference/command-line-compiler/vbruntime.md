---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
ms.openlocfilehash: a1988fcd19c6629d85ae0e739681fd39fe033c0d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843864"
---
# <a name="-vbruntime"></a>-vbruntime
Indica che il compilatore deve compilare senza un riferimento alla libreria di runtime di Visual Basic oppure con un riferimento a una libreria di runtime specifica.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Argomenti  
 \-  
 Compilare senza un riferimento alla libreria di Runtime di Visual Basic.  
  
 \+  
 Eseguire la compilazione con un riferimento per il valore predefinito della libreria di Runtime di Visual Basic.  
  
 \*  
 Compilare senza un riferimento alla libreria di Runtime di Visual Basic e incorporare funzionalità di base dalla libreria di Runtime di Visual Basic nell'assembly.  
  
 `path`  
 Eseguire la compilazione con un riferimento alla libreria (DLL) specificato.  
  
## <a name="remarks"></a>Note  
 Il `-vbruntime` opzione del compilatore consente di specificare che il compilatore deve compilare senza un riferimento alla libreria di Runtime di Visual Basic. Se esegue la compilazione senza un riferimento alla libreria di Runtime di Visual Basic, vengono registrati errori o avvisi in costrutti di linguaggio o codice che generano una chiamata a un helper di runtime di Visual Basic. (Un *helper di runtime di Visual Basic* è una funzione definita nel VisualBasic che viene chiamato in fase di esecuzione per l'esecuzione di un linguaggio specifico di semantico.)  
  
 Il `-vbruntime+` opzione produce lo stesso comportamento che si verifica se nessun `-vbruntime` viene specificata l'opzione. È possibile usare la `-vbruntime+` opzione per eseguire l'override precedente `-vbruntime` commutatori.  
  
 La maggior parte degli oggetti del `My` tipo non sono disponibili quando si usa la `-vbruntime-` o `-vbruntime:path` opzioni.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Incorporamento di funzionalità di base di Runtime di Visual Basic  
 Il `-vbruntime*` opzione consente di eseguire la compilazione senza un riferimento a una libreria di runtime. Al contrario, la funzionalità di base dalla libreria di Runtime di Visual Basic è incorporata nell'assembly utente. È possibile usare questa opzione se l'applicazione viene eseguita su piattaforme che non contengono il runtime di Visual Basic.  
  
 I membri di runtime seguenti sono incorporati:  
  
-   Classe <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   Metodo <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   Metodo <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   Metodo <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack> Costante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr> Costante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf> Costante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed> Costante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf> Costante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine> Costante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar> Costante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString> Costante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab> Costante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> Costante  
  
-   Alcuni oggetti del `My` tipo  
  
 Se si esegue la compilazione usando il `-vbruntime*` opzione e il codice fa riferimento a un membro dalla libreria di Runtime di Visual Basic che non sono incorporati con le funzionalità di base, il compilatore restituisce un errore che indica che il membro non è disponibile.  
  
## <a name="referencing-a-specified-library"></a>Riferimento a una libreria specificata  
 È possibile usare il `path` argomento per la compilazione con un riferimento a una libreria di runtime personalizzato anziché il valore predefinito della libreria di Runtime di Visual Basic.  
  
 Se il valore per il `path` argomento è un percorso completo di una DLL, il compilatore userà tale file come libreria di runtime. Se il valore per il `path` argomento non è un percorso completo di una DLL, il compilatore Visual Basic cercherà le DLL identificata nella cartella corrente prima di tutto. Quindi cercherà nel percorso specificato usando il [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) opzione del compilatore. Se il `-sdkpath` l'opzione del compilatore non viene utilizzato, il compilatore eseguirà la ricerca per la DLL identificata nella cartella di .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il `-vbruntime` opzione per la compilazione con un riferimento a una libreria personalizzata.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Vedere anche

- [Core di Visual Basic: nuova modalità di compilazione in Visual Studio 2010 SP1](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
