---
title: "'<typename>' è un tipo delegato"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 7056bbf2b4de26feba3bfbe0e02b3239311271c9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84382172"
---
# <a name="typename-is-a-delegate-type"></a>'\<typename>' è un tipo delegato
' \<typename> ' è un tipo delegato. La costruzione del delegato consente solo una singola espressione AddressOf come elenco di argomenti. Spesso è possibile usare un'espressione AddressOf anziché una costruzione di delegati.  
  
 Una `New` clausola che crea un'istanza di una classe Delegate fornisce un elenco di argomenti non valido al costruttore del delegato.  
  
 È possibile specificare una sola `AddressOf` espressione quando si crea una nuova istanza del delegato.  
  
 Questo errore può verificarsi se non si passano argomenti al costruttore del delegato, se si passa più di un argomento o se si passa un solo argomento che non è un' `AddressOf` espressione valida.  
  
 **ID errore:** BC32008  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Usare una singola `AddressOf` espressione nell'elenco di argomenti per la classe delegata nella `New` clausola.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore New](../operators/new-operator.md)
- [Operatore AddressOf](../operators/addressof-operator.md)
- [Delegati](../../programming-guide/language-features/delegates/index.md)
- [Procedura: richiamare un metodo delegato](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
