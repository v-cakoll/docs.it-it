---
title: 'Procedura: Creare un database in modo dinamico'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb7f23c4-4572-4c38-9898-a287807d070c
ms.openlocfilehash: e5d66b49782d5f26b6d487e655aca6fbd6bdfb1a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623856"
---
# <a name="how-to-dynamically-create-a-database"></a>Procedura: Creare un database in modo dinamico
In LINQ to SQL viene eseguito il mapping di un modello a oggetti a un database relazionale. Per descrivere la struttura del database relazionale è possibile eseguire il mapping basato sull'attributo o usare un file di mapping esterno. Entrambi gli scenari dispongono di informazioni sul database relazionale sufficienti per creare una nuova istanza del database mediante il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>.  
  
 Il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> crea una replica del database includendo solo le informazioni codificate nel modello a oggetti. I file e gli attributi di mapping del modello a oggetti potrebbero non codificare tutte le informazioni sulla struttura di un database esistente. Le informazioni sul mapping non rappresentano il contenuto di funzioni definite dall'utente, stored procedure, trigger o vincoli CHECK. Questo comportamento è sufficiente per vari tipi di database.  
  
 È possibile usare il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> in un numero illimitato di scenari, specialmente se è nota la disponibilità di un provider di dati come Microsoft SQL Server 2008. Gli scenari tipici includono i seguenti:  
  
- Si compila un'applicazione che viene installata automaticamente in un sistema del cliente.  
  
- Si compila un'applicazione client che richiede un database locale per salvare il proprio stato offline.  
  
 È inoltre possibile usare il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> con SQL Server mediante un file con estensione mdf o con un nome di catalogo, a seconda della stringa di connessione. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] usa la stringa di connessione per definire il database da creare e il server su cui dovrà essere creato il database.  
  
> [!NOTE]
>  Se possibile, usare la sicurezza integrata di Windows per connettersi al database in modo che non vengano richieste le password nella stringa di connessione.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene fornito un esempio della creazione di un nuovo database denominato MyDVDs.mdf.  
  
 [!code-csharp[DLinqSubmittingChanges#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#5)]
 [!code-vb[DLinqSubmittingChanges#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#5)]  
  
## <a name="example"></a>Esempio  
 È possibile usare il modello a oggetti per creare un database eseguendo le operazioni seguenti:  
  
 [!code-csharp[DLinqSubmittingChanges#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#6)]
 [!code-vb[DLinqSubmittingChanges#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#6)]  
  
## <a name="example"></a>Esempio  
 Quando si compila un'applicazione che viene installata automaticamente in un sistema del cliente, verificare se il database già esiste e rilasciarlo prima di crearne uno nuovo. La classe <xref:System.Data.Linq.DataContext> fornisce i metodi <xref:System.Data.Linq.DataContext.DatabaseExists%2A> e <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> per semplificare tale processo.  
  
 Nell'esempio seguente viene illustrato un modo in cui è possibile usare questi metodi per implementare tale approccio:  
  
 [!code-csharp[DLinqSubmittingChanges#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#7)]
 [!code-vb[DLinqSubmittingChanges#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>Vedere anche

- [Mapping basato su attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md) (Mapping esterno)
- [Mapping del tipo SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Creazione e invio di modifiche dei dati](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
