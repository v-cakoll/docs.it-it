---
title: Operatori numerici e di confronto
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 7e7af725864aa191f092055fa32b403093321aa5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781291"
---
# <a name="numeric-and-comparison-operators"></a>Operatori numerici e di confronto

Gli operatori aritmetici e di confronto funzionano correttamente in Common Language Runtime (CLR), ad eccezione di quanto descritto di seguito:

- In SQL non è supportato l'operatore modulo per i numeri a virgola mobile.

- In SQL non è supportato l'operatore aritmetico unchecked.

- Gli operatori di incremento e decremento provocano effetti collaterali quando vengono usati in espressioni che non possono essere replicate in SQL e, di conseguenza, non sono supportati.

## <a name="supported-operators"></a>Operatori supportati

In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono supportati gli operatori riportati di seguito.

- Operatori aritmetici di base:

  - `+`

  - `-` (sottrazione)

  - `*`

  - `/`

  - Divisione con valori integer di Visual Basic (`\`)

  - `%` (`Mod` di Visual Basic)

  - `<<`

  - `>>`

  - `-` (negazione unaria)

- Operatori di confronto di base:

  - `=` di Visual Basic e `==` di C#

  - `<>` di Visual Basic e `!=` di C#

  - `Is/IsNot` Visual Basic

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a>Vedere anche

- [Tipi di dati e funzioni](data-types-and-functions.md)
- [Operatori C#](../../../../../csharp/language-reference/operators/index.md)
- [Operatori](../../../../../visual-basic/language-reference/operators/index.md)
