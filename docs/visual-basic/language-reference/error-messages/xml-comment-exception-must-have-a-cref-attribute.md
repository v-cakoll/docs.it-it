---
title: L'eccezione del commento XML deve avere un attributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 2e57dc63cb7ad8b2e061296a082d6fa79b464f08
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592033"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>L'eccezione del commento XML deve avere un attributo 'cref'
Il tag di > \<exception fornisce un modo per documentare le eccezioni che possono essere generate da un metodo. L'attributo `cref` obbligatorio indica il nome di un membro, che viene controllato dal generatore di documentazione. Se il membro esiste, viene convertito nel nome canonico dell'elemento nel file di documentazione.  
  
 **ID errore:** BC42319  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Aggiungere l'attributo `cref` all'eccezione come segue:  
  
    xml  
    '''<exception cref="member">Descrizione</exception>  
    ```  
  
## See also

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md)
