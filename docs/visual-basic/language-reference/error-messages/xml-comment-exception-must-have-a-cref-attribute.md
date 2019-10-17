---
title: L'eccezione del commento XML deve avere un attributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321169"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>L'eccezione del commento XML deve avere un attributo 'cref'

Il tag \<exception > fornisce un modo per documentare le eccezioni che possono essere generate da un metodo. L'attributo `cref` obbligatorio indica il nome di un membro, che viene controllato dal generatore di documentazione. Se il membro esiste, viene convertito nel nome canonico dell'elemento nel file di documentazione.

**ID errore:** BC42319

## <a name="to-correct-this-error"></a>Per correggere l'errore

Aggiungere l'attributo `cref` all'eccezione come segue:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>Vedere anche

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
