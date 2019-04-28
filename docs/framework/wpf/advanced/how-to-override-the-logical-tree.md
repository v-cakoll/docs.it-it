---
title: "Procedura: Eseguire l'override dell'albero logico"
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: bf3459fff1a90326794d6713dd39c73596b0e960
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768446"
---
# <a name="how-to-override-the-logical-tree"></a>Procedura: Eseguire l'override dell'albero logico
Benché nella maggior parte dei casi non sia necessario, gli autori di controlli avanzati hanno la possibilità di eseguire l'override dell'albero logico.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come creare una sottoclasse <xref:System.Windows.Controls.StackPanel> all'override dell'albero logico, in questo caso per imporre un comportamento che il pannello può avere solo e verrà eseguito solo il rendering di un singolo elemento figlio. Benché non si tratti necessariamente di un comportamento utile, viene presentato come mezzo per illustrare lo scenario di override del normale albero logico di un elemento.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Per altre informazioni sull'albero logico, vedere [Strutture ad albero in WPF](trees-in-wpf.md).
