---
title: La variabile utilizza un tipo di automazione non supportato in Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: d369930752989ff69ee17359e85118f3af4b70b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766890"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>La variabile utilizza un tipo di automazione non supportato in Visual Basic

Si è provato a usare una variabile definita in una libreria dei tipi o una raccolta di oggetti con un tipo di dati non supportato da Visual Basic.

## <a name="to-correct-this-error"></a>Per correggere l'errore

- Usare una variabile di un tipo riconosciuto da Visual Basic.

     -oppure-

- Se si verifica questo errore quando si usa `FileGet` oppure `FileGetObject`, assicurarsi che il file si sta tentando di usare è stato scritto con `FilePut` o `FilePutObject`.

## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
