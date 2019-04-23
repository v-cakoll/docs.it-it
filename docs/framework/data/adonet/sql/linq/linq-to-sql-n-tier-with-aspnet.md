---
title: Più livelli di LINQ to SQL con ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 80c12d1c9f290657a6e005063d9cc77a17354abd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103733"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>Più livelli di LINQ to SQL con ASP.NET
Nelle applicazioni [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], usare il controllo server Web <xref:System.Web.UI.WebControls.LinqDataSource> . Il controllo gestisce la maggior parte della logica necessaria per eseguire una query su [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], passare i dati al browser, recuperarli e inviarli a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , che quindi aggiorna il database. Configurare il controllo nel markup in modo che sia in grado di gestire tutto il trasferimento dei dati tra [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e il browser. Poiché il controllo gestisce le interazioni con il livello di presentazione e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gestisce la comunicazione con il livello dati, lo stato attivo principale nelle applicazioni [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] a più livelli è nella scrittura della regola business personalizzata.  
  
 Per altre informazioni sulle `LINQDataSource`, vedere [Cenni preliminari sul controllo Server Web LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100)).  
  
## <a name="see-also"></a>Vedere anche

- [Applicazioni a più livelli e remote con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
