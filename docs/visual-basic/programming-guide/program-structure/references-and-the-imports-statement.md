---
title: Riferimenti e istruzione Imports (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 051351c2fa0648de54bbfd36b1630ec1cd49d6f0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Riferimenti e istruzione Imports (Visual Basic)
È possibile rendere gli oggetti esterni disponibili al progetto scegliendo il **Aggiungi riferimento** comando il **progetto** menu. Riferimenti in Visual Basic possono puntare a assembly, ovvero come librerie dei tipi, ma contengono ulteriori informazioni.  
  
## <a name="the-imports-statement"></a>Istruzione Imports  
 Gli assembly includono uno o più spazi dei nomi. Quando si aggiunge un riferimento a un assembly, è inoltre possibile aggiungere un `Imports` istruzione a un modulo che controlla la visibilità degli spazi dei nomi dell'assembly all'interno del modulo. Il `Imports` istruzione fornisce un contesto di ambito che consente di utilizzare solo la parte dello spazio dei nomi necessari per fornire un riferimento univoco.  
  
 Il `Imports` istruzione presenta la sintassi seguente:  
  
 `Imports` [`|``Aliasname` =] `Namespace`  
  
 `Aliasname` fa riferimento a un nome breve, che è possibile utilizzare all'interno di codice per fare riferimento a uno spazio dei nomi importato. `Namespace` è uno spazio dei nomi disponibile tramite un riferimento al progetto, tramite una definizione all'interno del progetto o tramite una precedente `Imports` istruzione.  
  
 Un modulo può contenere un numero qualsiasi di `Imports` istruzioni. È necessario specificarle dopo qualsiasi `Option` istruzioni, se presente, ma prima di qualsiasi altro codice.  
  
> [!NOTE]
>  Non confondere i riferimenti di progetto con il `Imports` istruzione o `Declare` istruzione. Riferimenti al progetto rendono oggetti esterni, ad esempio oggetti negli assembly, disponibili per i progetti di Visual Basic. Il `Imports` istruzione viene utilizzata per semplificare l'accesso ai riferimenti del progetto, ma non fornisce accesso a questi oggetti. Il `Declare` istruzione viene utilizzata per dichiarare un riferimento a una routine esterna in una libreria di collegamento dinamico (DLL).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Utilizzo degli alias con l'istruzione Imports  
 Il `Imports` istruzione semplifica l'accesso ai metodi delle classi, eliminando la necessità di tipo in modo esplicito il nome completo dei riferimenti. Gli alias consentono di assegnare un nome più descrittivo solo una parte di uno spazio dei nomi. Ad esempio, il ritorno a capo/avanzamento riga sequenza che provoca un'unica parte di testo da visualizzare su più righe fa parte del <xref:Microsoft.VisualBasic.ControlChars> modulo il <xref:Microsoft.VisualBasic?displayProperty=nameWithType> dello spazio dei nomi. Per utilizzare questa costante in un programma senza un alias, è necessario digitare il codice seguente:  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 `Imports` le istruzioni devono essere sempre le prime righe immediatamente dopo eventuali `Option` istruzioni in un modulo. Frammento di codice seguente viene illustrato come importare e assegnare un alias per il <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> modulo:  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 I riferimenti futuri a questo spazio dei nomi possono essere notevolmente inferiore:  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 Se un `Imports` istruzione non include un nome di alias, gli elementi definiti nello spazio dei nomi importato possono essere usati nel modulo senza qualifica. Se viene specificato il nome dell'alias, deve essere utilizzato come qualificatore per i nomi dei contenuti all'interno di tale spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.ControlChars>  
 <xref:Microsoft.VisualBasic>  
   
 [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Procedura: Creare e usare assembly dalla riga di comando](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
