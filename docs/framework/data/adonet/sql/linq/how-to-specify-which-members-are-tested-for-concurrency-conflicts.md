---
title: 'Procedura: Specificare per quali membri viene eseguito il test dei conflitti di concorrenza'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
ms.openlocfilehash: a690e95cadad4ed089fe1bb3ba6fea541a57411f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076302"
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a>Procedura: Specificare per quali membri viene eseguito il test dei conflitti di concorrenza
Applicare una delle tre enumerazioni al [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> proprietà su un <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per specificare quali membri devono essere incluse nell'aggiornamento controlla per il rilevamento dei conflitti di concorrenza ottimistica.  
  
 La proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>, di cui è stato eseguito il mapping in fase di progettazione, viene usata insieme alle funzionalità di concorrenza in fase di esecuzione in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Per altre informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
> [!NOTE]
>  I valori del membro originali vengono confrontati con lo stato corrente del database, a condizione che nessun membro sia designato come `IsVersion=true`. Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
 Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a>Per usare sempre questo membro per il rilevamento dei conflitti  
  
1.  Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> su `Always`.  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a>Per non usare mai questo membro per il rilevamento dei conflitti  
  
1.  Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> su `Never`.  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a>Per usare questo membro per il rilevamento dei conflitti solo quando il valore del membro è stato modificato dall'applicazione  
  
1.  Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> su `WhenChanged`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene specificato che gli oggetti `HomePage` non dovranno mai essere testati durante i controlli di aggiornamento. Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [Creazione e invio di modifiche dei dati](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
