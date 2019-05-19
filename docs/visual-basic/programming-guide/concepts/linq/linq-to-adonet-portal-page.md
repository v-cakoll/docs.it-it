---
title: LINQ to ADO.NET (pagina portale)
ms.date: 07/20/2015
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
ms.openlocfilehash: 7713d134650305c4e2d930a43c8b443b86448786
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882541"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (pagina portale)
[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] Consente di eseguire query su un oggetto enumerabile in ADO.NET tramite la [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] modello di programmazione.  
  
> [!NOTE]
>  La documentazione di [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] si trova nella sezione ADO.NET di .NET Framework SDK: [LINQ e ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).
  
 Sono disponibili tre diverse tecnologie [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] ADO.NET: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] e [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] offre un supporto più completo e ottimizzato per l'esecuzione di query su <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] consente di eseguire query direttamente sugli schemi di database di SQL Server e [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] consente di eseguire query su [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 Il <xref:System.Data.DataSet> è uno dei componenti maggiormente usati in ADO.NET e rappresenta un elemento chiave del modello di programmazione disconnesso basato su ADO.NET. Nonostante l'importanza che lo contraddistingue, tuttavia, <xref:System.Data.DataSet> ha solo funzionalità limitate di query.  
  
 [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] consente di compilare funzionalità di esecuzione di query più complesse nell'oggetto <xref:System.Data.DataSet> usando la stessa funzionalità di query disponibile per molte altre origini dati.  
  
 Per altre informazioni, vedere [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] fornisce un'infrastruttura di runtime per la gestione di dati relazionali come oggetti. In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] viene eseguito il mapping del modello dati di un database relazionale a un modello a oggetti espresso nel linguaggio di programmazione dello sviluppatore. Quando l'applicazione viene eseguita, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] converte in SQL le query LINQ (Language Integrated Query) nel modello a oggetti e le invia al database per l'esecuzione. Quando il database restituisce i risultati, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] li converte di nuovo in oggetti che è possibile modificare.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] include il supporto di stored procedure e funzioni definite dall'utente nel database e dell'ereditarietà nel modello a oggetti.  
  
 Per altre informazioni, vedere [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Tramite [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)], i dati relazionali vengono esposti come oggetti nell'ambiente .NET. Ciò rende il livello di oggetto una destinazione ideale per il supporto di [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], consentendo agli sviluppatori di formulare query sul database a partire dal linguaggio usato per compilare la logica di business. Questa funzionalità è nota come [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. Per altre informazioni, vedere [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Vedere anche

- [LINQ e ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)
- [LINQ (Language-Integrated Query) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
