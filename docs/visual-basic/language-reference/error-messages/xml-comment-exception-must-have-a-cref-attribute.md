---
title: Eccezione del commento XML deve avere un &#39; cref &#39; attributo
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0c22c9cd9415faf17d027c3751d166662a92b50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a>Eccezione del commento XML deve avere un &#39; cref &#39; attributo
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
