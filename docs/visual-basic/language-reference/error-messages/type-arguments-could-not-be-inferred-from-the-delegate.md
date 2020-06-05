---
title: Impossibile dedurre argomenti tipo dal delegato
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: f29e92c8245e33c0418d9a387070b03f645c331e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362748"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a>Impossibile dedurre argomenti tipo dal delegato
Un'istruzione di assegnazione usa `AddressOf` per assegnare l'indirizzo di un oggetto generico a un delegato, ma non fornisce alcun argomento di tipo alla routine generica.  
  
 Di norma, quando si richiama un tipo generico, si fornisce un argomento di tipo per ogni parametro di tipo definito dal tipo generico. Se non si specifica alcun argomento di tipo, il compilatore prova a dedurre i tipi da passare ai parametri di tipo. Se il contesto non fornisce informazioni sufficienti per consentire al compilatore di dedurre i tipi, genera un errore.  
  
 **ID errore:** BC36564  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Specificare gli argomenti di tipo per la routine generica nell'espressione `AddressOf` .  
  
## <a name="see-also"></a>Vedere anche

- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Operatore AddressOf](../operators/addressof-operator.md)
- [Generic Procedures in Visual Basic](../../programming-guide/language-features/data-types/generic-procedures.md)
- [Type List](../statements/type-list.md)
- [Metodi di estensione](../../programming-guide/language-features/procedures/extension-methods.md)
