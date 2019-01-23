---
title: Nome &#39; &lt;name&gt; &#39; non è dichiarato
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: e52b93980cfc2d162d35b86bd93ce9eeb9875c9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574820"
---
# <a name="name-39ltnamegt39-is-not-declared"></a>Nome &#39; &lt;name&gt; &#39; non è dichiarato
Un'istruzione fa riferimento a un elemento di programmazione, ma il compilatore non trova un elemento con quel nome esatto.  
  
 **ID errore:** BC30451  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Controllare l'ortografia del nome nell'istruzione di riferimento. Visual Basic è tra maiuscole e minuscole, ma qualsiasi altra variazione nell'ortografia viene considerata come un nome completamente diverso. Si noti che il carattere di sottolineatura (`_`) fa parte del nome e quindi dell'ortografia.  
  
2. Verificare di avere l'operatore di accesso ai membri (`.`) tra un oggetto e il relativo membro. Ad esempio, se è presente un controllo <xref:System.Windows.Forms.TextBox> denominato `TextBox1`, per accedere alla relativa proprietà <xref:System.Windows.Forms.TextBoxBase.Text%2A> occorre digitare `TextBox1.Text`. Se invece si digita `TextBox1Text`, viene creato un nome diverso.  
  
3. Se l'ortografia sia corretta e la sintassi di accesso ai membri qualsiasi oggetto sia corretta, verificare che l'elemento è stato dichiarato. Per altre informazioni, vedere [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).  
  
4. Se è stata dichiarata l'elemento di programmazione, controllare che si trova nell'ambito. Se l'istruzione di riferimento è di fuori dell'area di dichiarazione di elemento di programmazione, è necessario qualificare il nome dell'elemento. Per altre informazioni, vedere [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).  

5. Se non si usa un nome completo del tipo o un nome di tipi e membri (ad esempio, il codice fa riferimento a una proprietà come `MethodInfo.Name` invece di `System.Reflection.MethodInfo.Name`), aggiungere un' [istruzione Imports](../statements/imports-statement-net-namespace-and-type.md).

6. Se si sta tentando di compilare un progetto in stile SDK (un progetto con un \*file con estensione vbproj che inizia con la riga `<Project Sdk="Microsoft.NET.Sdk">`) e il messaggio di errore fa riferimento a un tipo o membro nell'assembly VisualBasic, configurare l'applicazione per eseguire la compilazione con un riferimento alla libreria di Runtime di Visual Basic. Per impostazione predefinita, un subset della libreria è incorporato nell'assembly in un progetto basato su SDK.

   Ad esempio, nell'esempio seguente non viene compilato perché il <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> metodo nebyla nalezena. Non è incorporato nel subset di Runtime di Visual Basic incluso con l'applicazione.  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb)]

   Per risolvere questo errore, aggiungere il `<VBRuntime>Default</VBRuntime>` elemento ai progetti `<PropertyGroup>` sezione, come i seguente di file di progetto Visual Basic.

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a>Vedere anche

- [Riepilogo delle dichiarazioni e delle costanti](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)
- [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
