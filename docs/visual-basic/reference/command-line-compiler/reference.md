---
title: /reference (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f8c6851802afa818cc80b3f6d7eafc2ef47ac689
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="reference-visual-basic"></a>/reference (Visual Basic)
Indica al compilatore di rendere disponibili per il progetto in corso di compilazione informazioni sui tipi negli assembly specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`fileList`|Obbligatorio. Elenco di nomi di file di assembly delimitato da virgole. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.|  
  
## <a name="remarks"></a>Note  
 I file importati devono contenere i metadati dell'assembly. Solo i tipi pubblici sono visibili all'esterno dell'assembly. Il [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opzione Importa metadati da un modulo.  
  
 Se si fa riferimento a un assembly (Assembly a) che a sua volta fa riferimento a un altro assembly (Assembly B), è necessario fare riferimento all'Assembly B se:  
  
-   Un tipo dell'assembly A eredita da un tipo o implementa un'interfaccia dall'assembly B.  
  
-   Viene richiamato un campo, una proprietà, un evento o un metodo che presenta un tipo restituito o un tipo di parametro proveniente dall'assembly B.  
  
 Utilizzare [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) per specificare la directory in cui si trova uno o più riferimenti agli assembly.  
  
 Per il compilatore di riconoscere un tipo in un assembly (non un modulo), è necessario imporre la risoluzione del tipo. Un esempio di come è possibile farlo consiste nel definire un'istanza del tipo. Esistono altri modi risolvere i nomi dei tipi in un assembly per il compilatore. Ad esempio, se si eredita da un tipo in un assembly, il nome del tipo quindi diventa nota al compilatore.  
  
 Il file di risposta Vbc.rsp, i riferimenti utilizzati comunemente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assembly, viene utilizzato per impostazione predefinita. Utilizzare `/noconfig` se non si desidera al compilatore di usare Vbc.rsp.  
  
 La forma breve di `/reference` è `/r`.  
  
## <a name="example"></a>Esempio  
 Nel codice riportato di seguito viene compilato il file di origine `Input.vb` e viene fatto riferimento agli assembly di `Metad1.dll` e `Metad2.dll` per generare `Out.exe`.  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
