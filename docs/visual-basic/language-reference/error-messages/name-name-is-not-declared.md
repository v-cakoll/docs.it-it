---
title: Nome '<name>' non dichiarato
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: dfa1d1600c7943e503b4f5ec2e2b8ecd6fbb9fe0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254192"
---
# <a name="name-name-is-not-declared"></a>Il nome\<' name >' non è dichiarato
Un'istruzione fa riferimento a un elemento di programmazione, ma il compilatore non trova un elemento con quel nome esatto.  
  
 **ID errore:** BC30451  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Controllare l'ortografia del nome nell'istruzione di riferimento. Visual Basic non fa distinzione tra maiuscole e minuscole, ma qualsiasi altra variazione nell'ortografia viene considerata un nome completamente diverso. Si noti che il carattere di sottolineatura (`_`) fa parte del nome e quindi dell'ortografia.  
  
2. Verificare di disporre dell'operatore di accesso ai membri`.`() tra un oggetto e il relativo membro. Ad esempio, se è presente un controllo <xref:System.Windows.Forms.TextBox> denominato `TextBox1`, per accedere alla relativa proprietà <xref:System.Windows.Forms.TextBoxBase.Text%2A> occorre digitare `TextBox1.Text`. Se invece si digita `TextBox1Text`, viene creato un nome diverso.  
  
3. Se l'ortografia è corretta e la sintassi di qualsiasi accesso ai membri dell'oggetto è corretta, verificare che l'elemento sia stato dichiarato. Per altre informazioni, vedere [elementi dichiarati](../../programming-guide/language-features/declared-elements/index.md).  
  
4. Se l'elemento di programmazione è stato dichiarato, verificare che sia nell'ambito. Se l'istruzione di riferimento è esterna all'area che dichiara l'elemento di programmazione, potrebbe essere necessario qualificare il nome dell'elemento. Per altre informazioni, vedere [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).  

5. Se non si utilizza un tipo completo o un nome di membro (ad esempio, il codice fa riferimento a una proprietà come `MethodInfo.Name` `System.Reflection.MethodInfo.Name`anziché), aggiungere un' [istruzione Imports](../statements/imports-statement-net-namespace-and-type.md).

6. Se si tenta di compilare un progetto in stile SDK (un progetto con un \*file con estensione vbproj che inizia con la riga `<Project Sdk="Microsoft.NET.Sdk">`) e il messaggio di errore fa riferimento a un tipo o a un membro nell'assembly Microsoft. VisualBasic. dll, configurare l'applicazione in modo da compilare con un riferimento alla libreria di runtime Visual Basic. Per impostazione predefinita, un subset della libreria è incorporato nell'assembly in un progetto di tipo SDK.

   Ad esempio, l'esempio seguente non viene compilato perché non <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ChangeType%2A?displayProperty=fullName> è possibile trovare il metodo. Non è incorporato nel subset del runtime Visual Basic incluso nell'applicazione.  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb?highlight=7)]

   Per risolvere questo errore, aggiungere l' `<VBRuntime>Default</VBRuntime>` elemento alla sezione Projects `<PropertyGroup>` , come mostrato nel file di progetto Visual Basic seguente.

   [!code-xml[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a>Vedere anche

- [Riepilogo delle dichiarazioni e delle costanti](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)
- [Convenzioni di denominazione Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
