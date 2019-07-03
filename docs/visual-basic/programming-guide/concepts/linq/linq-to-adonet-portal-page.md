---
title: LINQ to ADO.NET (pagina portale)
ms.date: 07/20/2015
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
ms.openlocfilehash: 850e154b40e69cc655ee1b59161351b0b2898033
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539376"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (pagina portale)
LINQ to ADO.NET consente di eseguire una query su qualsiasi oggetto enumerabile in ADO.NET tramite la [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] modello di programmazione.  
  
> [!NOTE]
>  LINQ to ADO.NET documentazione si trova nella sezione ADO.NET di .NET Framework SDK: [LINQ e ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).
  
 Esistono tre ADO.NET separato [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] tecnologie: LINQ to DataSet, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]e LINQ to Entities. LINQ to DataSet fornisce più completo e ottimizzato per l'esecuzione di query tramite il <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] consente di eseguire query direttamente gli schemi di database di SQL Server e LINQ to Entities consente di eseguire una query un Entity Data Model.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> è uno dei componenti maggiormente usati in ADO.NET ed è un elemento chiave del modello di programmazione disconnessa su cui si basa ADO.NET. Nonostante l'importanza che lo contraddistingue, tuttavia, <xref:System.Data.DataSet> ha solo funzionalità limitate di query.  
  
 LINQ to DataSet consente di compilare funzionalità di query più complesse in <xref:System.Data.DataSet> usando la stessa funzionalità di query disponibile per molte altre origini dati.  
  
 Per altre informazioni, vedere [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] fornisce un'infrastruttura di runtime per la gestione di dati relazionali come oggetti. In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] viene eseguito il mapping del modello dati di un database relazionale a un modello a oggetti espresso nel linguaggio di programmazione dello sviluppatore. Quando l'applicazione viene eseguita, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] converte in SQL le query LINQ (Language Integrated Query) nel modello a oggetti e le invia al database per l'esecuzione. Quando il database restituisce i risultati, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] li converte di nuovo in oggetti che è possibile modificare.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] include il supporto di stored procedure e funzioni definite dall'utente nel database e dell'ereditarietà nel modello a oggetti.  
  
 Per altre informazioni, vedere [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Tramite Entity Data Model, dati relazionali vengono esposti come oggetti nell'ambiente .NET. Ciò rende il livello di oggetto una destinazione ideale per il supporto di [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], consentendo agli sviluppatori di formulare query sul database a partire dal linguaggio usato per compilare la logica di business. Questa funzionalità è nota come LINQ to Entities. Per altre informazioni, vedere [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Vedere anche

- [LINQ e ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)
- [LINQ (Language-Integrated Query) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
