---
title: 'Procedura: Restituire set di righe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: b853a6f2175009cbcbc01c14a6732b98e37e1a7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003067"
---
# <a name="how-to-return-rowsets"></a>Procedura: Restituire set di righe
In questo esempio viene restituito un rowset dal database e viene incluso un parametro di input per filtrare il risultato.  
  
 Quando si esegue un stored procedure che restituisce un set di righe, si usa una classe di risultato che archivia i *risultati* restituiti dal stored procedure. Per ulteriori informazioni, vedere [analisi LINQ to SQL codice sorgente](analyzing-linq-to-sql-source-code.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è rappresentata una stored procedure che restituisce righe di clienti e usa un parametro di input per restituire solo le righe in cui è elencata "London" come città del cliente. In questo esempio si presuppone una classe `CustomersByCityResult` enumerabile.  
  
```sql  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [stored procedure](stored-procedures.md)
- [Download di database di esempio](downloading-sample-databases.md)
