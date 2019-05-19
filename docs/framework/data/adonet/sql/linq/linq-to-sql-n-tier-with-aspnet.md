---
title: Più livelli di LINQ to SQL con ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 85ead36d1d927084c11dca1bd73a192b16e4ab7b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880758"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>Più livelli di LINQ to SQL con ASP.NET
Nelle applicazioni ASP.NET che utilizzano [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], si utilizza il <xref:System.Web.UI.WebControls.LinqDataSource> controllo server Web. Il controllo gestisce la maggior parte della logica necessaria per eseguire una query su [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], passare i dati al browser, recuperarli e inviarli a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , che quindi aggiorna il database. Configurare il controllo nel markup in modo che sia in grado di gestire tutto il trasferimento dei dati tra [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e il browser. Poiché il controllo gestisce le interazioni con il livello di presentazione, e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gestisce la comunicazione con il livello di dati, lo stato attivo principale nelle applicazioni a più livelli di ASP.NET è nella scrittura logica di business personalizzata.  
  
 Per altre informazioni sulle `LINQDataSource`, vedere [Cenni preliminari sul controllo Server Web LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100)).  
  
## <a name="see-also"></a>Vedere anche

- [Applicazioni a più livelli e remote con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
