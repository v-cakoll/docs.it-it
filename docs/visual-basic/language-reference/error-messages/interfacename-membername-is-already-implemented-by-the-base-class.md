---
title: "'<interfacename>. <membername>'è già implementata dalla classe base'<baseclassname>'. Prevista nuova implementazione di <type> presuppone"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 5943eff5fa7e68da9905e3e589eea264c06943c1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593310"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a>'\<nomeinterfaccia >. \<nomeMembro >' è già implementata della classe di base\<nomeclassebase >'. Prevista nuova implementazione di \<tipo > si presuppone che
Una proprietà, routine o evento in una classe derivata Usa un `Implements` clausola che specifica un membro di interfaccia che è già implementato nella classe di base.  
  
 Una classe derivata può reimplementare un membro di interfaccia implementato dalla sua classe base. Questo non equivale a eseguire l'override dell'implementazione della classe base. Per altre informazioni, vedere [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42015  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se si intende reimplementare il membro di interfaccia, non occorre fare nulla. Codice della classe derivata accede al membro reimplementato a meno che non si utilizza il `MyBase` una parola chiave per accedere all'implementazione della classe di base.  
  
- Se non si intende reimplementare il membro di interfaccia, rimuovere la clausola `Implements` dalla dichiarazione di proprietà, routine o evento.  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
