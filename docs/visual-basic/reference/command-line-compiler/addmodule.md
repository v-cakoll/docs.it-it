---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: fbe3634d1fbc03acd56ef7276d65fd54493b9806
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002410"
---
# <a name="-addmodule"></a>-addmodule
Fa sì che il compilatore renda disponibili per il progetto in compilazione tutte le informazioni sui tipi presenti nei file specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Argomenti  
 `fileList`  
 Obbligatorio. Elenco delimitato da virgole di file che contengono metadati ma che non contengono manifesti di assembly. I nomi di file contenenti spazi devono essere racchiusi tra virgolette ("").  
  
## <a name="remarks"></a>Note  
 I file elencati dal parametro `fileList` devono essere creati con l'opzione `-target:module` o con un altro compilatore equivalente a `-target:module`.  
  
 Tutti i moduli aggiunti con `-addmodule` devono trovarsi nella stessa directory del file di output in fase di esecuzione. In altre termini, è possibile specificare un modulo in qualsiasi directory in fase di compilazione, ma il modulo deve trovarsi nella directory dell'applicazione in fase di esecuzione. In caso contrario, viene ricevuto un errore <xref:System.TypeLoadException>.  
  
 Se si specifica (in modo implicito o esplicito) qualsiasi opzione di[destinazione (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) diversa da `-target:module` con `-addmodule`, i file passati a `-addmodule` diventano parte dell'assembly del progetto. Per eseguire un file di output con uno o più file aggiunti con `-addmodule`, è necessario un assembly.  
  
 Usare [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) per importare metadati da un file che contiene un assembly.  
  
> [!NOTE]
> L'opzione `-addmodule` non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente crea un modulo.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 Il codice seguente importa i tipi del modulo.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 Quando si esegue `t1`, viene restituito `802`.  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
