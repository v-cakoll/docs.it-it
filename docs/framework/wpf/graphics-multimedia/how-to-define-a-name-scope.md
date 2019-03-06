---
title: 'Procedura: Definire un ambito del nome'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: 6afb59550d774109c62c283905495c76b0834b3d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370371"
---
# <a name="how-to-define-a-name-scope"></a>Procedura: Definire un ambito del nome
Per aggiungere un'animazione con <xref:System.Windows.Media.Animation.Storyboard> nel codice, è necessario creare un <xref:System.Windows.NameScope> e registrare i nomi degli oggetti di destinazione con l'elemento che è proprietario di tale ambito dei nomi. Nell'esempio seguente, un <xref:System.Windows.NameScope> viene creato per `myMainPanel`. Due pulsanti, `button1` e `button2`, vengono aggiunti al pannello di e i relativi nomi registrati. Diverse animazioni e un <xref:System.Windows.Media.Animation.Storyboard> vengono creati. Lo storyboard <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo viene usato per avviare le animazioni.  
  
 In quanto `button1`, `button2`, e `myMainPanel` condividono tutti lo stesso ambito del nome, uno di essi può essere utilizzato con il <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo per avviare le animazioni.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a>Vedere anche
- [Animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
