---
title: Tipo &#39; &lt;nomeTipo&gt; &#39; non è definito
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 8e303a9ac6529fbbc818c94497a16463897fb0c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496127"
---
# <a name="type-39lttypenamegt39-is-not-defined"></a>Tipo &#39; &lt;nomeTipo&gt; &#39; non è definito
L'istruzione ha fatto riferimento a un tipo che non è stato definito. È possibile definire un tipo in un'istruzione di dichiarazione, ad esempio `Enum`, `Structure`, `Class`, o `Interface`.  
  
 **ID errore:** BC30002  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Assicurarsi che la definizione del tipo e il relativo riferimento usino entrambi la stessa ortografia.  
  
-   Verificare che la definizione del tipo sia accessibile al riferimento. Ad esempio, se il tipo è in un altro modulo ed è stato dichiarato `Private`spostare la definizione del tipo per il riferimento modulo o dichiararla `Public`.  
  
-   Assicurarsi che lo spazio dei nomi del tipo viene ridefinito non all'interno del progetto. Se si tratta, usare il `Global` parola chiave per qualificare completamente il nome del tipo. Ad esempio, se un progetto definisce uno spazio dei nomi denominato `System`, il <xref:System.Object?displayProperty=nameWithType> tipo non è accessibile, a meno che non è completo, con la `Global` parola chiave: `Global.System.Object`.  
  
-   Se il tipo è definito, ma la libreria di oggetto o una libreria dei tipi in cui viene definito non è registrata in Visual Basic, scegliere **Aggiungi riferimento** nel **progetto** menu e quindi selezionare l'oggetto sia appropriato raccolta o libreria dei tipi.  
  
-   Assicurarsi che il tipo è in un assembly che fa parte del profilo di .NET Framework di destinazione. Per altre informazioni, vedere [Risoluzione dei problemi relativi agli errori di impostazione di .NET Framework come destinazione](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>Vedere anche
- [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)
