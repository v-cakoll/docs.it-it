---
title: LINQ to ADO.NET (pagina portale)
ms.date: 07/20/2015
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
ms.openlocfilehash: d5d7ba8230ae9737d4938c1c8c55f7cd4330b117
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636497"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (pagina portale)
LINQ to ADO.NET consente di eseguire una query su qualsiasi oggetto enumerabile in ADO.NET utilizzando il modello di programmazione LINQ (Language-Integrated Query).  
  
> [!NOTE]
> La documentazione di LINQ to ADO.NET si trova nella sezione ADO.NET dell'SDK .NET Framework: [LINQ e ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).
  
 Sono disponibili tre tecnologie LINQ (Language-Integrated Query) separate: LINQ to DataSet, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]e LINQ to Entities. LINQ to DataSet offre un supporto più completo e ottimizzato per l'esecuzione di query su <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] consente di eseguire query direttamente sugli schemi di database di SQL Server e LINQ to Entities consente di eseguire query su Entity Data Model.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> è uno dei componenti maggiormente usati in ADO.NET ed è un elemento chiave del modello di programmazione disconnessa su cui si basa ADO.NET. Nonostante l'importanza che lo contraddistingue, tuttavia, <xref:System.Data.DataSet> ha solo funzionalità limitate di query.  
  
 LINQ to DataSet consente di compilare funzionalità di esecuzione di query più complesse nell'oggetto <xref:System.Data.DataSet> usando la stessa funzionalità di query disponibile per molte altre origini dati.  
  
 Per altre informazioni, vedere [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] fornisce un'infrastruttura di runtime per la gestione di dati relazionali come oggetti. In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] viene eseguito il mapping del modello dati di un database relazionale a un modello a oggetti espresso nel linguaggio di programmazione dello sviluppatore. Quando l'applicazione viene eseguita, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] converte in SQL le query LINQ (Language Integrated Query) nel modello a oggetti e le invia al database per l'esecuzione. Quando il database restituisce i risultati, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] li converte di nuovo in oggetti che è possibile modificare.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] include il supporto di stored procedure e funzioni definite dall'utente nel database e dell'ereditarietà nel modello a oggetti.  
  
 Per altre informazioni, vedere [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Tramite Entity Data Model, i dati relazionali vengono esposti come oggetti nell'ambiente .NET. Questo rende il livello di oggetto una destinazione ideale per il supporto LINQ, consentendo agli sviluppatori di formulare query sul database dal linguaggio utilizzato per compilare la logica di business. Questa funzionalità è nota come LINQ to Entities. Per altre informazioni, vedere [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Vedere anche

- [LINQ e ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)
- [LINQ (Language-Integrated Query) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
