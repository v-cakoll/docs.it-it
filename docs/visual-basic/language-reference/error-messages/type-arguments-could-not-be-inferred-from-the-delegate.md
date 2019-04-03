---
title: Impossibile dedurre argomenti tipo dal delegato
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 1024cf6f2c1fa112db29cb710eef190a5022d3af
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838599"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a>Impossibile dedurre argomenti tipo dal delegato
Un'istruzione di assegnazione usa `AddressOf` per assegnare l'indirizzo di un oggetto generico a un delegato, ma non fornisce alcun argomento di tipo alla routine generica.  
  
 Di norma, quando si richiama un tipo generico, si fornisce un argomento di tipo per ogni parametro di tipo definito dal tipo generico. Se non si specifica alcun argomento di tipo, il compilatore prova a dedurre i tipi da passare ai parametri di tipo. Se il contesto non fornisce informazioni sufficienti per consentire al compilatore di dedurre i tipi, genera un errore.  
  
 **ID errore:** BC36564  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Specificare gli argomenti di tipo per la routine generica nell'espressione `AddressOf` .  
  
## <a name="see-also"></a>Vedere anche

- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Generic Procedures in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [Elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md)
- [Metodi di estensione](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
