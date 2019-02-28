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
ms.openlocfilehash: f3396eb3e758dc456d86de80246de24349680f2e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973041"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Riferimenti e istruzione Imports (Visual Basic)
È possibile rendere gli oggetti esterni disponibili al progetto scegliendo il **Aggiungi riferimento** comando le **progetto** menu. I riferimenti in Visual Basic possono puntare agli assembly, che sono come le librerie dei tipi ma contengono ulteriori informazioni.  
  
## <a name="the-imports-statement"></a>Istruzione Imports  
 Assembly includono uno o più spazi dei nomi. Quando si aggiunge un riferimento a un assembly, è anche possibile aggiungere un `Imports` istruzione a un modulo che controlla la visibilità degli spazi dei nomi dell'assembly all'interno del modulo. Il `Imports` istruzione fornisce un contesto dell'ambito che ti permette di usare solo la parte dello spazio dei nomi necessari per fornire un riferimento univoco.  
  
 Il `Imports` istruzione ha la sintassi seguente:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname` fa riferimento a un nome breve che è possibile usare all'interno del codice per fare riferimento a uno spazio dei nomi importato. `Namespace` è uno spazio dei nomi disponibile tramite un riferimento al progetto, tramite una definizione all'interno del progetto o una precedente `Imports` istruzione.  
  
 Un modulo può contenere un numero qualsiasi di `Imports` istruzioni. È necessario specificarle dopo qualsiasi `Option` (istruzioni), se presente, ma prima di qualsiasi altro codice.  
  
> [!NOTE]
>  Non confondere i riferimenti di progetto con il `Imports` istruzione o il `Declare` istruzione. I riferimenti al progetto rendere gli oggetti esterni, ad esempio oggetti negli assembly, disponibili per i progetti Visual Basic. Il `Imports` istruzione viene usata per semplificare l'accesso ai riferimenti del progetto, ma non fornisce l'accesso a questi oggetti. Il `Declare` istruzione viene usata per dichiarare un riferimento a una routine esterna in una libreria di collegamento dinamico (DLL).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Utilizzo degli alias con l'istruzione Imports  
 Il `Imports` istruzione semplifica l'accesso ai metodi delle classi, eliminando la necessità di tipizzare in modo esplicito i nomi completi dei riferimenti. Gli alias consentono di assegnare un nome più descrittivo a una sola parte di uno spazio dei nomi. Ad esempio, il ritorno a capo/avanzamento riga sequenza che provoca un'unica parte di testo da visualizzare su più righe fa parte del <xref:Microsoft.VisualBasic.ControlChars> modulo nel <xref:Microsoft.VisualBasic?displayProperty=nameWithType> dello spazio dei nomi. Per usare questa costante in un programma senza un alias, è necessario digitare il codice seguente:  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 `Imports` le istruzioni devono sempre essere le prime righe immediatamente successive alle `Option` istruzioni in un modulo. Il frammento di codice seguente viene illustrato come importare e assegnare un alias per il <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> modulo:  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 I riferimenti futuri di questo spazio dei nomi possono essere notevolmente più brevi:  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 Se un `Imports` istruzione non include un nome di alias, gli elementi definiti nello spazio dei nomi importato possono essere usati nel modulo senza qualifica. Se viene specificato il nome dell'alias, deve essere usato come qualificatore per i nomi dei contenuti all'interno di tale spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Assembly in .NET](../../../standard/assembly/index.md)
- [Procedura: Creare e usare assembly dalla riga di comando](../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
