---
title: 'Procedura: specificare per quali membri viene eseguito il test dei conflitti di concorrenza'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0c65299f48db3ba727cece673e6a7df2d9cd8872
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a>Procedura: specificare per quali membri viene eseguito il test dei conflitti di concorrenza
Applicare una delle tre enumerazioni al [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> proprietà in un <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per specificare quali membri devono essere inclusi nell'aggiornamento verifica il rilevamento dei conflitti di concorrenza ottimistica.  
  
 La proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>, di cui è stato eseguito il mapping in fase di progettazione, viene usata insieme alle funzionalità di concorrenza in fase di esecuzione in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Per ulteriori informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
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
 [Procedura: gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [Creazione e invio di modifiche dei dati](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
