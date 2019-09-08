---
title: Modifica di dati con stored procedure
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
ms.openlocfilehash: 46c92301b717e285c4c18241f84d0069069c7bdc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783522"
---
# <a name="modifying-data-with-stored-procedures"></a>Modifica di dati con stored procedure
Le stored procedure possono accettare dati come parametri di input e possono restituire dati come parametri di output, set di risultati o valori restituiti. Nell'esempio seguente vengono illustrati l'invio e la ricezione di parametri di input, parametri di output e valori restituiti in ADO.NET. Viene inserito un nuovo record in una tabella in cui la colonna della chiave primaria è una colonna Identity di un database SQL Server.  
  
> [!NOTE]
> Se si usano stored procedure SQL Server per modificare o eliminare dati tramite <xref:System.Data.SqlClient.SqlDataAdapter>, assicurarsi di non usare SET NOCOUNT ON nella definizione della stored procedure. Con tale comando il totale restituito delle righe interessate è pari a zero e tale situazione viene interpretata da `DataAdapter` come un conflitto di concorrenza. In questo caso verrà generata un'eccezione <xref:System.Data.DBConcurrencyException>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio viene utilizzata la stored procedure seguente per inserire una nuova categoria nella tabella delle **categorie** **Northwind** . Il stored procedure accetta il valore nella colonna **CategoryName** come parametro di input e utilizza la funzione SCOPE_IDENTITY () per recuperare il nuovo valore del campo Identity, **CategoryID**, e restituirlo in un parametro di output. L'istruzione return utilizza la funzione@ROWCOUNT @ per restituire il numero di righe inserite.  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 Nell'esempio di codice seguente viene usata la stored procedure `InsertCategory` sopra indicata come origine per <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> di <xref:System.Data.SqlClient.SqlDataAdapter>. Il parametro di output `@Identity` e il valore restituito verranno riflessi in <xref:System.Data.DataSet> dopo l'inserimento del record nel database quando viene chiamato il metodo `Update` di <xref:System.Data.SqlClient.SqlDataAdapter>. Nel codice viene inoltre recuperato il valore restituito:  
  
> [!NOTE]
> Quando si usa <xref:System.Data.OleDb.OleDbDataAdapter>, è necessario specificare i parametri <xref:System.Data.ParameterDirection> con di **returnValue** prima degli altri parametri.  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Recupero e modifica di dati in ADO.NET](retrieving-and-modifying-data.md)
- [DataAdapter e DataReader](dataadapters-and-datareaders.md)
- [Esecuzione di un comando](executing-a-command.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
