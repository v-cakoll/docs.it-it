---
title: Operatori numerici e di confronto
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 9b31fd2d819afbb1e589ad74f23ec139830c68b8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212167"
---
# <a name="numeric-and-comparison-operators"></a>Operatori numerici e di confronto
Gli operatori aritmetici e di confronto funzionano correttamente in Common Language Runtime (CLR), ad eccezione di quanto descritto di seguito:  
  
-   In SQL non è supportato l'operatore modulo per i numeri a virgola mobile.  
  
-   In SQL non è supportato l'operatore aritmetico unchecked.  
  
-   Gli operatori di incremento e decremento provocano effetti collaterali quando vengono usati in espressioni che non possono essere replicate in SQL e, di conseguenza, non sono supportati.  
  
## <a name="supported-operators"></a>Operatori supportati  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono supportati gli operatori riportati di seguito.  
  
-   Operatori aritmetici di base:  
  
    -   `+`  
  
    -   `-` (sottrazione)  
  
    -   `*`  
  
    -   `/`  
  
    -   Divisione con valori integer di Visual Basic (`\`)  
  
    -   `%` (`Mod` di Visual Basic)  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-` (negazione unaria)  
  
-   Operatori di confronto di base:  
  
    -   `=` di Visual Basic e `==` di C#  
  
    -   `<>` di Visual Basic e `!=` di C#  
  
    -   `Is/IsNot` Visual Basic  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [Operatori C#](../../../../../../docs/csharp/language-reference/operators/index.md)
- [Operatori](../../../../../visual-basic/language-reference/operators/index.md)
