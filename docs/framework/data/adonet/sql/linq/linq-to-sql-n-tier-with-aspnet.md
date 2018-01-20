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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5069c518998ca1d93f6e1ce94d76c8d0c7da07bd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>Più livelli di LINQ to SQL con ASP.NET
Nelle applicazioni [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], usare il controllo server Web <xref:System.Web.UI.WebControls.LinqDataSource> . Il controllo gestisce la maggior parte della logica necessaria per eseguire una query su [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], passare i dati al browser, recuperarli e inviarli a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , che quindi aggiorna il database. Configurare il controllo nel markup in modo che sia in grado di gestire tutto il trasferimento dei dati tra [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e il browser. Poiché il controllo gestisce le interazioni con il livello di presentazione e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gestisce la comunicazione con il livello dati, lo stato attivo principale nelle applicazioni [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] a più livelli è nella scrittura della regola business personalizzata.  
  
 Per ulteriori informazioni su `LINQDataSource`, vedere [NIB: Panoramica del controllo Server Web LinqDataSource](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## <a name="see-also"></a>Vedere anche  
 [Applicazioni a più livelli e remote con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
