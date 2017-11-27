---
title: "Più livelli di LINQ to SQL con ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 643f38c495a57dd98c3524eaf82cdbdfe42220c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>Più livelli di LINQ to SQL con ASP.NET
Nelle applicazioni [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], usare il controllo server Web <xref:System.Web.UI.WebControls.LinqDataSource> . Il controllo gestisce la maggior parte della logica necessaria per eseguire una query su [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], passare i dati al browser, recuperarli e inviarli a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , che quindi aggiorna il database. Configurare il controllo nel markup in modo che sia in grado di gestire tutto il trasferimento dei dati tra [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e il browser. Poiché il controllo gestisce le interazioni con il livello di presentazione e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gestisce la comunicazione con il livello dati, lo stato attivo principale nelle applicazioni [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] a più livelli è nella scrittura della regola business personalizzata.  
  
 Per altre informazioni su `LINQDataSource`, vedere [NIB: Cenni preliminari sul controllo server Web LinqDataSource](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## <a name="see-also"></a>Vedere anche  
 [A più livelli e applicazioni Remote con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
