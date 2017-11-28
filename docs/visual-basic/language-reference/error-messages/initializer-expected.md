---
title: Previsto inizializzatore
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords: BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46ff91ec240212571f7ec9f26e82d9d128263545
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="initializer-expected"></a>Previsto inizializzatore
Si è provato a dichiarare un'istanza di una classe utilizzando un inizializzatore di oggetto in cui l'inizializzazione di elenco è vuoto, come illustrato nell'esempio seguente.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 Almeno un campo o una proprietà deve essere inizializzato nell'elenco di inizializzatori, come illustrato nell'esempio seguente.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **ID errore:** BC30996  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Inizializzare almeno un campo o proprietà nell'inizializzatore o non utilizzare un inizializzatore di oggetto.  
  
## <a name="see-also"></a>Vedere anche  
 [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
