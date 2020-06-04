---
title: La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase.New' o a 'MyClass.New' (nessun costruttore accessibile senza parametri)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 2b9d2568fb64e4af72733ad1f3dee58aaee650e5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402979"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a>La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase.New' o a 'MyClass.New' (nessun costruttore accessibile senza parametri)
La prima istruzione di questo ' Sub New ' deve essere una chiamata a' MyBase. New ' o a' MyClass. New ' perché la classe base ' \<basename> ' di ' \<derivedname> ' non ha un'Sub New ' accessibile che può essere chiamato senza argomenti.  
  
 In una classe derivata ogni costruttore deve chiamare un costruttore della classe base ( `MyBase.New` ). Se la classe base dispone di un costruttore senza parametri accessibile alle classi derivate, `MyBase.New` può essere chiamato automaticamente. In caso contrario, è necessario chiamare un costruttore della classe base con parametri e questa operazione non può essere eseguita automaticamente. In questo caso, la prima istruzione di ogni costruttore della classe derivata deve chiamare un costruttore con parametri sulla classe di base o chiamare un altro costruttore nella classe derivata che effettua una chiamata al costruttore della classe base.  
  
 **ID errore:** BC30148  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Chiamare `MyBase.New` la fornitura dei parametri obbligatori o chiamare un costruttore peer che esegue tale chiamata.  
  
     Se, ad esempio, la classe base ha un costruttore dichiarato come `Public Sub New(ByVal index as Integer)` , la prima istruzione nel costruttore della classe derivata potrebbe essere `MyBase.New(100)` .  
  
## <a name="see-also"></a>Vedere anche

- [Nozioni fondamentali sull'ereditarietà](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
