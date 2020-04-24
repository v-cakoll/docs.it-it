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
ms.openlocfilehash: 8c7789c6af7b82ecb40ecd73d09f64aa1da3fd4b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005048"
---
# <a name="-vbruntime"></a>-vbruntime
Indica che il compilatore deve compilare senza un riferimento alla libreria di runtime di Visual Basic oppure con un riferimento a una libreria di runtime specifica.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Argomenti  
 \-  
 Eseguire la compilazione senza un riferimento alla libreria di runtime Visual Basic.  
  
 \+  
 Compilare con un riferimento alla libreria di runtime Visual Basic predefinita.  
  
 \*  
 Eseguire la compilazione senza un riferimento alla libreria di runtime Visual Basic e incorporare la funzionalità di base dalla libreria di runtime Visual Basic nell'assembly.  
  
 `path`  
 Compilare con un riferimento alla libreria (DLL) specificata.  
  
## <a name="remarks"></a>Osservazioni  
 L' `-vbruntime` opzione del compilatore consente di specificare che il compilatore deve compilare senza un riferimento alla libreria di runtime Visual Basic. Se si compila senza un riferimento alla libreria di runtime Visual Basic, gli errori o gli avvisi vengono registrati nel codice o nei costrutti di linguaggio che generano una chiamata a un helper del runtime di Visual Basic. Un *helper Visual Basic Runtime* è una funzione definita in Microsoft. VisualBasic. dll che viene chiamata in fase di esecuzione per eseguire una semantica di linguaggio specifica.  
  
 L' `-vbruntime+` opzione produce lo stesso comportamento che si verifica se `-vbruntime` non è specificata alcuna opzione. È possibile usare l' `-vbruntime+` opzione per eseguire l' `-vbruntime` override delle opzioni precedenti.  
  
 La maggior parte degli `My` oggetti del tipo non sono disponibili quando `-vbruntime-` si `-vbruntime:path` usano le opzioni o.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Incorporamento della funzionalità di base di Visual Basic Runtime  
 L' `-vbruntime*` opzione consente di compilare senza un riferimento a una libreria di Runtime. Al contrario, la funzionalità di base della libreria di runtime Visual Basic è incorporata nell'assembly utente. È possibile usare questa opzione se l'applicazione viene eseguita su piattaforme che non contengono il runtime di Visual Basic.  
  
 Sono incorporati i membri runtime seguenti:  
  
- Classe <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
- Metodo <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
- Metodo <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
- Metodo <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
- <xref:Microsoft.VisualBasic.Constants.vbBack>costante  
  
- <xref:Microsoft.VisualBasic.Constants.vbCr>costante  
  
- <xref:Microsoft.VisualBasic.Constants.vbCrLf>costante  
  
- <xref:Microsoft.VisualBasic.Constants.vbFormFeed>costante  
  
- <xref:Microsoft.VisualBasic.Constants.vbLf>costante  
  
- <xref:Microsoft.VisualBasic.Constants.vbNewLine>costante  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullChar>costante  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullString>costante  
  
- <xref:Microsoft.VisualBasic.Constants.vbTab>costante  
  
- <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>costante  
  
- Alcuni oggetti del `My` tipo  
  
 Se si esegue la compilazione `-vbruntime*` con l'opzione e il codice fa riferimento a un membro dalla libreria di runtime Visual Basic che non è incorporato con la funzionalità di base, il compilatore restituisce un errore che indica che il membro non è disponibile.  
  
## <a name="referencing-a-specified-library"></a>Riferimento a una libreria specificata  
 È possibile usare l' `path` argomento per compilare con un riferimento a una libreria di runtime personalizzata anziché la libreria di runtime Visual Basic predefinita.  
  
 Se il valore per l' `path` argomento è un percorso completo di una dll, il compilatore utilizzerà tale file come libreria di Runtime. Se il valore dell' `path` argomento non è un percorso completo di una dll, il Visual Basic compilatore cercherà prima la DLL identificata nella cartella corrente. Verrà quindi cercata nel percorso specificato tramite l'opzione del compilatore [-sdkpath (](../../../visual-basic/reference/command-line-compiler/sdkpath.md) . Se non `-sdkpath` si usa l'opzione del compilatore, il compilatore cercherà la DLL identificata nella cartella .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l' `-vbruntime` opzione per compilare con un riferimento a una libreria personalizzata.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Vedi anche

- [Visual Basic Core-nuova modalità di compilazione in Visual Studio 2010 SP1](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath (](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
