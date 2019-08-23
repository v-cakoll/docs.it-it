---
title: Riferimenti e istruzione Imports (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 99afa42994dd09d0b5faaeaf534fbc4b41816998
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962484"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Riferimenti e istruzione Imports (Visual Basic)
È possibile rendere disponibili oggetti esterni per il progetto scegliendo il comando **Aggiungi riferimento** dal menu **progetto** . I riferimenti in Visual Basic possono puntare ad assembly, che sono simili alle librerie dei tipi ma contengono ulteriori informazioni.  
  
## <a name="the-imports-statement"></a>Istruzione Imports  
 Gli assembly includono uno o più spazi dei nomi. Quando si aggiunge un riferimento a un assembly, è anche possibile aggiungere un' `Imports` istruzione a un modulo che controlla la visibilità degli spazi dei nomi dell'assembly all'interno del modulo. L' `Imports` istruzione fornisce un contesto di ambito che consente di utilizzare solo la parte dello spazio dei nomi necessaria per fornire un riferimento univoco.  
  
 L' `Imports` istruzione ha la sintassi seguente:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname`fa riferimento a un nome breve che è possibile utilizzare all'interno del codice per fare riferimento a uno spazio dei nomi importato. `Namespace`è uno spazio dei nomi disponibile tramite un riferimento al progetto, tramite una definizione all'interno del progetto o tramite `Imports` un'istruzione precedente.  
  
 Un modulo può contenere un numero qualsiasi `Imports` di istruzioni. Devono essere visualizzate dopo qualsiasi `Option` istruzione, se presente, ma prima di qualsiasi altro codice.  
  
> [!NOTE]
> Non confondere i riferimenti del progetto `Imports` con l'istruzione `Declare` o l'istruzione. I riferimenti al progetto rendono disponibili oggetti esterni, ad esempio oggetti negli assembly, per Visual Basic progetti. L' `Imports` istruzione viene utilizzata per semplificare l'accesso ai riferimenti del progetto, ma non fornisce l'accesso a tali oggetti. L' `Declare` istruzione viene utilizzata per dichiarare un riferimento a una procedura esterna in una libreria di collegamento dinamico (dll).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Utilizzo degli alias con l'istruzione Imports  
 L' `Imports` istruzione semplifica l'accesso ai metodi delle classi eliminando la necessità di digitare in modo esplicito i nomi completi dei riferimenti. Gli alias consentono di assegnare un nome amichevole a una sola parte di uno spazio dei nomi. Ad esempio, la sequenza ritorno a capo/avanzamento riga che causa la visualizzazione di una singola porzione di testo su più righe fa parte del <xref:Microsoft.VisualBasic.ControlChars> modulo <xref:Microsoft.VisualBasic?displayProperty=nameWithType> nello spazio dei nomi. Per usare questa costante in un programma senza un alias, è necessario digitare il codice seguente:  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 `Imports`le istruzioni devono essere sempre le prime righe immediatamente successive `Option` a qualsiasi istruzione in un modulo. Il frammento di codice seguente illustra come importare e assegnare un alias al <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> modulo:  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 I riferimenti futuri a questo spazio dei nomi possono essere notevolmente più brevi:  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 Se un' `Imports` istruzione non include un nome di alias, è possibile usare gli elementi definiti nello spazio dei nomi importato nel modulo senza qualifica. Se il nome dell'alias è specificato, deve essere usato come qualificatore per i nomi contenuti in tale spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Assembly in .NET](../../../standard/assembly/index.md)
- [Procedura: Creare e usare assembly dalla riga di comando](../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
