---
title: L'eccezione del commento XML deve avere un attributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: a11bfe261ffb8ded95f2e513aaddf00aa00f702e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266637"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>L'eccezione del commento XML deve avere un attributo 'cref'
Il \<eccezione > tag consente di documentare le eccezioni che possono essere generate da un metodo. Obbligatorio `cref` l'attributo specifica il nome di un membro, che viene controllato dal generatore di documentazione. Se il membro esiste, viene convertito al nome canonico dell'elemento nel file di documentazione.  
  
 **ID errore:** BC42319  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Aggiungere il `cref` attributo per l'eccezione come indicato di seguito:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
