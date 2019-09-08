---
title: 'Procedura: Inserire righe nel database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 8186b90a666a7b75ce626cccb7cc28af38de7c5b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781858"
---
# <a name="how-to-insert-rows-into-the-database"></a>Procedura: Inserire righe nel database

Per inserire righe in un database, è necessario aggiungere oggetti alla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] raccolta associata <xref:System.Data.Linq.Table%601> e quindi inviare le modifiche al database. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]converte le modifiche nei comandi SQL `INSERT` appropriati.

> [!NOTE]
> È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`. Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](customizing-insert-update-and-delete-operations.md).
>
> Gli sviluppatori che utilizzano Visual Studio possono utilizzare il Object Relational Designer per sviluppare stored procedure allo stesso scopo.

Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind. Per altre informazioni, vedere [Procedura: Connettersi a un database](how-to-connect-to-a-database.md).

### <a name="to-insert-a-row-into-the-database"></a>Per inserire una riga nel database

1. Creare un nuovo oggetto contenente i dati della colonna da inviare.

2. Aggiungere il nuovo oggetto alla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` raccolta associata alla tabella di destinazione nel database.

3. Inviare le modifiche al database.

## <a name="example"></a>Esempio

L'esempio di codice seguente consente di creare un nuovo oggetto di tipo `Order` e di popolarlo con i valori corretti. Il nuovo oggetto viene quindi aggiunto alla raccolta `Order`. Infine viene inviata la modifica al database come una nuova riga nella tabella `Orders`.

[!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
[!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Procedura: Gestione dei conflitti di modifica](how-to-manage-change-conflicts.md)
- [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Creazione e invio di modifiche dei dati](making-and-submitting-data-changes.md)
