---
title: LINQ to ADO.NET (pagina portale)
ms.date: 07/20/2015
ms.assetid: 6bd269b4-3509-4688-b672-836008704182
ms.openlocfilehash: d65f041751a9418d0eebd3f92fd33a414cbed699
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44209316"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (pagina portale)
[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] consente di eseguire una query in qualsiasi oggetto enumerabile in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] usando il modello di programmazione [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].  
  
> [!NOTE]
>  La documentazione di [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] si trova nella sezione ADO.NET di .NET Framework SDK: [LINQ e ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).  
  
 Sono disponibili tre diverse tecnologie [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] ADO.NET: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] e [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] offre un supporto più completo e ottimizzato per l'esecuzione di query su <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] consente di eseguire query direttamente sugli schemi di database di SQL Server e [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] consente di eseguire query su [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> è uno dei componenti maggiormente usati in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] ed è un elemento chiave del modello di programmazione disconnesso su cui è basato [!INCLUDE[vstecado](~/includes/vstecado-md.md)]. Nonostante l'importanza che lo contraddistingue, tuttavia, <xref:System.Data.DataSet> ha solo funzionalità limitate di query.  
  
 [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] consente di compilare funzionalità di esecuzione di query più complesse nell'oggetto <xref:System.Data.DataSet> usando la stessa funzionalità di query disponibile per molte altre origini dati.  
  
 Per altre informazioni, vedere [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] fornisce un'infrastruttura di runtime per la gestione di dati relazionali come oggetti. In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] viene eseguito il mapping del modello dati di un database relazionale a un modello a oggetti espresso nel linguaggio di programmazione dello sviluppatore. Quando l'applicazione viene eseguita, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] converte in SQL le query LINQ (Language Integrated Query) nel modello a oggetti e le invia al database per l'esecuzione. Quando il database restituisce i risultati, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] li converte di nuovo in oggetti che è possibile modificare.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] include il supporto di stored procedure e funzioni definite dall'utente nel database e dell'ereditarietà nel modello a oggetti.  
  
 Per altre informazioni, vedere [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Tramite [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)], i dati relazionali vengono esposti come oggetti nell'ambiente .NET. Ciò rende il livello di oggetto una destinazione ideale per il supporto di [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], consentendo agli sviluppatori di formulare query sul database a partire dal linguaggio usato per compilare la logica di business. Questa funzionalità è nota come [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. Per altre informazioni, vedere [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Vedere anche

- [LINQ e ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)  
- [LINQ (Language-Integrated Query) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
