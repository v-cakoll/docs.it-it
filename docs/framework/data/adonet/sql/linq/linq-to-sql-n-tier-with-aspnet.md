---
title: Più livelli di LINQ to SQL con ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 1770d84053b57e05d1a4e41919a3eb4122dc73a3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793029"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>Più livelli di LINQ to SQL con ASP.NET
Nelle applicazioni ASP.NET che usano [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], è possibile usare <xref:System.Web.UI.WebControls.LinqDataSource> il controllo server Web. Il controllo gestisce la maggior parte della logica necessaria per eseguire una query su [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], passare i dati al browser, recuperarli e inviarli a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , che quindi aggiorna il database. Configurare il controllo nel markup in modo che sia in grado di gestire tutto il trasferimento dei dati tra [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e il browser. Poiché il controllo gestisce le interazioni con il livello di presentazione e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gestisce la comunicazione con il livello dati, lo stato attivo principale nelle applicazioni multilivello di ASP.NET è la scrittura della logica di business personalizzata.  
  
 Per ulteriori informazioni su `LINQDataSource`, vedere [Cenni preliminari sul controllo server Web LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100)).  
  
## <a name="see-also"></a>Vedere anche

- [Applicazioni a più livelli e remote con LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
