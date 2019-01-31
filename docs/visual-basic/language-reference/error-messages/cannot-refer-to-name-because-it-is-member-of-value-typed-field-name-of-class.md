---
title: Impossibile fare riferimento a '<name>' perché è un membro del campo di valori '<name>' della classe '<classname>' che ha 'System.MarshalByRefObject' come classe base
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: c29d3def2299dc1d7e3b084b3408b3f919addc63
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279585"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a>Impossibile fare riferimento a '\<nome >' perché è un membro del campo valori '\<nome >' della classe\<NomeClasse >' che ha 'System. MarshalByRefObject' come classe di base
Il `System.MarshalByRefObject` classe consente alle applicazioni che supportano l'accesso remoto a oggetti attraverso limiti di dominio. I tipi devono ereditare dal `MarshalByRejectObject` classe quando viene utilizzato il tipo superando i limiti di dominio di applicazione. Lo stato dell'oggetto non deve essere copiato perché i membri dell'oggetto non sono utilizzabili all'esterno del dominio applicazione in cui sono stati creati.  
  
 **ID errore:** BC30310  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare il riferimento per assicurarsi che il membro a cui si fa riferimento è valido.  
  
2.  Qualificare in modo esplicito il membro con il `Me` (parola chiave).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.MarshalByRefObject>
- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
