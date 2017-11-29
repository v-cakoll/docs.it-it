---
title: Impossibile dedurre argomenti tipo dal delegato
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords: BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 57a3a24af32d9eb85a0f905aa3a73a956723b6d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a>Impossibile dedurre argomenti tipo dal delegato
Un'istruzione di assegnazione usa `AddressOf` per assegnare l'indirizzo di un oggetto generico a un delegato, ma non fornisce alcun argomento di tipo alla routine generica.  
  
 Di norma, quando si richiama un tipo generico, si fornisce un argomento di tipo per ogni parametro di tipo definito dal tipo generico. Se non si specifica alcun argomento di tipo, il compilatore prova a dedurre i tipi da passare ai parametri di tipo. Se il contesto non fornisce informazioni sufficienti per consentire al compilatore di dedurre i tipi, genera un errore.  
  
 **ID errore:** BC36564  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Specificare gli argomenti di tipo per la routine generica nell'espressione `AddressOf` .  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Routine generiche in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [Elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md)  
 [Metodi di estensione](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
