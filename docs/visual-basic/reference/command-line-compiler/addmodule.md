---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: dd98b45d75ff421dc81666ed47695132a49bfa3a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524472"
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
  
## <a name="remarks"></a>Osservazioni  
 I file elencati dal `fileList` parametro devono essere creati con l' `-target:module` opzione o con un altro compilatore equivalente a. `-target:module`  
  
 Tutti i moduli aggiunti `-addmodule` con devono trovarsi nella stessa directory del file di output in fase di esecuzione. In altre termini, è possibile specificare un modulo in qualsiasi directory in fase di compilazione, ma il modulo deve trovarsi nella directory dell'applicazione in fase di esecuzione. In caso contrario, viene ricevuto un <xref:System.TypeLoadException> errore.  
  
 Se si specifica (in modo implicito o esplicito) qualsiasi opzione di[destinazione (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) `-target:module` diversa `-addmodule`da con, i file passati `-addmodule` a diventano parte dell'assembly del progetto. Per eseguire un file di output con uno o più file aggiunti con `-addmodule`, è necessario un assembly.  
  
 Use [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) per importare metadati da un file che contiene un assembly.  
  
> [!NOTE]
> L' `-addmodule` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente crea un modulo.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 Il codice seguente importa i tipi del modulo.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 Quando si esegue `t1`, viene restituito `802`.  
  
## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
