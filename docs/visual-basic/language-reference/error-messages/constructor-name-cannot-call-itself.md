---
title: Costruttore &#39; &lt;name&gt; &#39; non può chiamare se stesso
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 4a02277893147716098a3dcc327e221e0775d476
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662725"
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a>Costruttore &#39; &lt;name&gt; &#39; non può chiamare se stesso
Oggetto `Sub New` routine in una classe o struttura chiama se stessa.  
  
 È lo scopo di un costruttore per inizializzare un'istanza di una classe o struttura quando viene inizialmente creato. Una classe o struttura può avere diversi costruttori, purché dispongano di elenchi di parametri diversi. Un costruttore è autorizzato a chiamare un altro costruttore per eseguire le funzionalità oltre a un proprio. Ma non ha significato per un costruttore di chiamare se stesso e di fatto il risultato sarà una ricorsione infinita se è consentito.  
  
 **ID errore:** BC30298  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Controllare l'elenco di parametri del costruttore viene chiamato. Deve essere diverso da quello del costruttore effettua la chiamata.  
  
2.  Se non si intende chiamare un costruttore diverso, rimuovere il `Sub New` chiamare interamente.  
  
## <a name="see-also"></a>Vedere anche
- [Durata degli oggetti: Come gli oggetti vengono creati ed eliminati](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
