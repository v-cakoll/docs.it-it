---
title: Riferimenti e istruzione Imports
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 31b4fe001f2b8a62ac30488053c57cd186020421
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347270"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Riferimenti e istruzione Imports (Visual Basic)
È possibile rendere disponibili oggetti esterni per il progetto scegliendo il comando **Aggiungi riferimento** dal menu **progetto** . I riferimenti in Visual Basic possono puntare ad assembly, che sono simili alle librerie dei tipi ma contengono ulteriori informazioni.  
  
## <a name="the-imports-statement"></a>Istruzione Imports  
 Gli assembly includono uno o più spazi dei nomi. Quando si aggiunge un riferimento a un assembly, è anche possibile aggiungere un'istruzione `Imports` a un modulo che controlla la visibilità degli spazi dei nomi dell'assembly all'interno del modulo. L'istruzione `Imports` fornisce un contesto di ambito che consente di utilizzare solo la parte dello spazio dei nomi necessaria per fornire un riferimento univoco.  
  
 L'istruzione `Imports` presenta la sintassi seguente:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname` fa riferimento a un nome breve che è possibile usare all'interno del codice per fare riferimento a uno spazio dei nomi importato. `Namespace` è uno spazio dei nomi disponibile tramite un riferimento al progetto, tramite una definizione all'interno del progetto o tramite un'istruzione `Imports` precedente.  
  
 Un modulo può contenere un numero qualsiasi di istruzioni `Imports`. Devono essere visualizzate dopo qualsiasi istruzione `Option`, se presente, ma prima di qualsiasi altro codice.  
  
> [!NOTE]
> Non confondere i riferimenti del progetto con l'istruzione `Imports` o l'istruzione `Declare`. I riferimenti al progetto rendono disponibili oggetti esterni, ad esempio oggetti negli assembly, per Visual Basic progetti. L'istruzione `Imports` viene utilizzata per semplificare l'accesso ai riferimenti del progetto, ma non fornisce l'accesso a tali oggetti. L'istruzione `Declare` viene utilizzata per dichiarare un riferimento a una procedura esterna in una libreria di collegamento dinamico (DLL).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Utilizzo degli alias con l'istruzione Imports  
 L'istruzione `Imports` rende più semplice accedere ai metodi delle classi eliminando la necessità di digitare in modo esplicito i nomi completi dei riferimenti. Gli alias consentono di assegnare un nome amichevole a una sola parte di uno spazio dei nomi. Ad esempio, la sequenza ritorno a capo/avanzamento riga che determina la visualizzazione di una singola parte di testo su più righe fa parte del modulo <xref:Microsoft.VisualBasic.ControlChars> nello spazio dei nomi <xref:Microsoft.VisualBasic?displayProperty=nameWithType>. Per usare questa costante in un programma senza un alias, è necessario digitare il codice seguente:  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 le istruzioni `Imports` devono essere sempre le prime righe immediatamente successive alle istruzioni `Option` in un modulo. Il frammento di codice seguente illustra come importare e assegnare un alias al modulo <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType>:  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 I riferimenti futuri a questo spazio dei nomi possono essere notevolmente più brevi:  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 Se un'istruzione `Imports` non include un nome di alias, è possibile usare gli elementi definiti nello spazio dei nomi importato nel modulo senza qualifica. Se il nome dell'alias è specificato, deve essere usato come qualificatore per i nomi contenuti in tale spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Spazi dei nomi in Visual Basic](namespaces.md)
- [Assembly in .NET](../../../standard/assembly/index.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
