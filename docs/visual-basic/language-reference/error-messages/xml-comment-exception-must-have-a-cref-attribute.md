---
title: Eccezione del commento XML deve avere un &#39;cref&#39; attributo
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: abe9fe0f6216f81fa223fe83a122b580577e1c32
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "43255645"
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a>Eccezione del commento XML deve avere un &#39;cref&#39; attributo
Il \<eccezione > tag consente di documentare le eccezioni che possono essere generate da un metodo. Obbligatorio `cref` l'attributo specifica il nome di un membro, che viene controllato dal generatore di documentazione. Se il membro esiste, viene convertito al nome canonico dell'elemento nel file di documentazione.  
  
 **ID errore:** BC42319  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Aggiungere il `cref` attributo per l'eccezione come indicato di seguito:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
