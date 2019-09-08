---
title: 'Procedura: Specificare il controllo di conflitti di concorrenza'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: fd3db5eb5dc9b74d8ea33af56dd522cf2f3fecdb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781596"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a>Procedura: Specificare il controllo di conflitti di concorrenza
È possibile specificare in quali colonne del database deve essere effettuato il controllo dei conflitti di concorrenza quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Per altre informazioni, vedere [Procedura: Specificare i membri sottoposti a test per i](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)conflitti di concorrenza.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene specificato che il membro `HomePage` non dovrà mai essere testato durante i controlli di aggiornamento. Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Modello a oggetti LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedura: Personalizzare le classi di entità tramite l'editor di codice](how-to-customize-entity-classes-by-using-the-code-editor.md)
