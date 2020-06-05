---
title: L'eccezione del commento XML deve avere un attributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: c498675ab6ae616fb63d3d76ef60bcac7e247145
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406508"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>L'eccezione del commento XML deve avere un attributo 'cref'

Il \<exception> tag fornisce un modo per documentare le eccezioni che possono essere generate da un metodo. L' `cref` attributo required designa il nome di un membro, che viene controllato dal generatore di documentazione. Se il membro esiste, viene convertito nel nome canonico dell'elemento nel file di documentazione.

**ID errore:** BC42319

## <a name="to-correct-this-error"></a>Per correggere l'errore

Aggiungere l' `cref` attributo all'eccezione come segue:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>Vedere anche

- [\<exception>](../xmldoc/exception.md)
- [Procedura: Creare documentazione XML](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [Tag di commento XML](../xmldoc/index.md)
