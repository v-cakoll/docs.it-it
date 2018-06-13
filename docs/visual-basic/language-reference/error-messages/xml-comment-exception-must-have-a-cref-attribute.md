---
title: Eccezione del commento XML deve avere un &#39;cref&#39; attributo
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: ee91513ef94e2abbe01d3ac09796b7fdf8e129ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597383"
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a>Eccezione del commento XML deve avere un &#39;cref&#39; attributo
Il \<eccezione > tag fornisce un modo per documentare le eccezioni che possono essere generate da un metodo. Obbligatorio `cref` l'attributo specifica il nome di un membro, è selezionata per il generatore di documentazione. Se il membro esiste, viene convertito il nome canonico dell'elemento nel file di documentazione.  
  
 **ID errore:** BC42319  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Aggiungere il `cref` attributo all'eccezione, come indicato di seguito:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
