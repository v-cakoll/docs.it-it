---
title: "'<interfacename>.<membername>' è già implementata dalla classe base '<baseclassname>'. Prevista nuova implementazione di <type>"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 6525ae08b90cc530a8f6a469d35d9ab8c27fb5e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402824"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a>'\<interfacename>.\<membername>' è già implementata dalla classe base '\<baseclassname>'. Prevista nuova implementazione di \<type>
Una proprietà, una routine o un evento in una classe derivata usa una `Implements` clausola che specifica un membro di interfaccia già implementato nella classe di base.  
  
 Una classe derivata può reimplementare un membro di interfaccia implementato dalla sua classe base. Questo non equivale a eseguire l'override dell'implementazione della classe base. Per altre informazioni, vedere [Implements](../statements/implements-clause.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42015  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se si intende reimplementare il membro di interfaccia, non occorre fare nulla. Il codice della classe derivata accede al membro reimplementato a meno che non si usi la `MyBase` parola chiave per accedere all'implementazione della classe di base.  
  
- Se non si intende reimplementare il membro di interfaccia, rimuovere la clausola `Implements` dalla dichiarazione di proprietà, routine o evento.  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce](../../programming-guide/language-features/interfaces/index.md)
