---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 4e2f441863d6a8677593a257cdb2cc841634d47c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820243"
---
# <a name="exception-visual-basic"></a>\<exception> (Visual Basic)
Specifica le eccezioni che possono essere generate.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a>Parametri  
 `member`  
 Riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente. Il compilatore controlla che l'eccezione specificata esista e converte `member` nel nome canonico dell'elemento nel file XML di output. `member` deve essere racchiuso tra virgolette doppie (" ").  
  
 `description`  
 Descrizione.  
  
## <a name="remarks"></a>Note  
 Usare il `<exception>` tag per specificare le eccezioni che possono essere generate. Questo tag viene applicato a una definizione di metodo.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<exception>` tag per descrivere un'eccezione che il `IntDivide` funzione può generare.  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
