---
title: LINQ to ADO.NET (pagina portale)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b5cbbca716cc7de36541aecd630eb9a98815f5a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (pagina portale)
[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] consente di eseguire una query in qualsiasi oggetto enumerabile in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] usando il modello di programmazione [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].  
  
> [!NOTE]
>  La documentazione di [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] si trova nella sezione ADO.NET di .NET Framework SDK: [LINQ e ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).  
  
 Sono disponibili tre diverse tecnologie [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] ADO.NET: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] e [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] offre un supporto più completo e ottimizzato per l'esecuzione di query su <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] consente di eseguire query direttamente sugli schemi di database di [!INCLUDE[ssNoVersion](~/includes/ssnoversion-md.md)] e [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] consente di eseguire query su [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> è uno dei componenti maggiormente usati in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] ed è un elemento chiave del modello di programmazione disconnesso su cui è basato [!INCLUDE[vstecado](~/includes/vstecado-md.md)]. Nonostante l'importanza che lo contraddistingue, tuttavia, <xref:System.Data.DataSet> ha solo funzionalità limitate di query.  
  
 [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] consente di compilare funzionalità di esecuzione di query più complesse nell'oggetto <xref:System.Data.DataSet> usando la stessa funzionalità di query disponibile per molte altre origini dati.  
  
 Per altre informazioni, vedere [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] fornisce un'infrastruttura di runtime per la gestione di dati relazionali come oggetti. In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] viene eseguito il mapping del modello dati di un database relazionale a un modello a oggetti espresso nel linguaggio di programmazione dello sviluppatore. Quando l'applicazione viene eseguita, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] converte in SQL le query LINQ (Language Integrated Query) nel modello a oggetti e le invia al database per l'esecuzione. Quando il database restituisce i risultati, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] li converte di nuovo in oggetti che è possibile modificare.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] include il supporto di stored procedure e funzioni definite dall'utente nel database e dell'ereditarietà nel modello a oggetti.  
  
 Per altre informazioni, vedere [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Tramite [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)], i dati relazionali vengono esposti come oggetti nell'ambiente .NET. Ciò rende il livello di oggetto una destinazione ideale per il supporto di [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], consentendo agli sviluppatori di formulare query sul database a partire dal linguaggio usato per compilare la logica di business. Questa funzionalità è nota come [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. Per altre informazioni, vedere [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ e ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)  
 [LINQ (Language-Integrated Query) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
