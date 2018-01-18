---
title: Operatori numerici e di confronto
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 56558e790b8aee300da0a75ade7c0ac451a0eca1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
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
 [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [Operatori C#](http://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [Operatori](../../../../../visual-basic/language-reference/operators/index.md)
