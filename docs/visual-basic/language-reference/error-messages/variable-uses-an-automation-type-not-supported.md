---
title: La variabile utilizza un tipo di automazione non supportato
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: 944c0c63cd0d7ae7f9ff770fd123231464af1eaf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344833"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>La variabile utilizza un tipo di automazione non supportato in Visual Basic

Si è tentato di utilizzare una variabile definita in una libreria dei tipi o in una libreria di oggetti con tipo di dati non supportato da Visual Basic.

## <a name="to-correct-this-error"></a>Per correggere l'errore

- Usare una variabile di un tipo riconosciuto dal Visual Basic.

     -oppure-

- Se si verifica questo errore quando si usa `FileGet` o `FileGetObject`, assicurarsi che il file che si sta provando a usare sia stato scritto con `FilePut` o `FilePutObject`.

## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
