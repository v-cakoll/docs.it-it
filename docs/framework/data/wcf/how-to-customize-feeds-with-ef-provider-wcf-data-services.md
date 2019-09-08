---
title: 'Procedura: Personalizzare i feed con il provider di Entity Framework (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: fd16272e-36f2-415e-850e-8a81f2b17525
ms.openlocfilehash: 8f994065ea42d6fc522fa297cafa8c46a8164e67
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780160"
---
# <a name="how-to-customize-feeds-with-the-entity-framework-provider-wcf-data-services"></a>Procedura: Personalizzare i feed con il provider di Entity Framework (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] consente di personalizzare la serializzazione Atom in una risposta del servizio dati in modo che venga eseguito il mapping delle proprietà di un'entità agli elementi inutilizzati definiti nel protocollo AtomPub. In questo argomento viene illustrato come definire attributi di mapping per i tipi di entità in un modello di dati definito in un file con estensione edmx tramite il provider di Entity Framework. Per altre informazioni, vedere [personalizzazione del feed](feed-customization-wcf-data-services.md).  
  
 In questo argomento si modificherà manualmente il file con estensione edmx generato dallo strumento contenente il modello di dati. Il file deve essere modificato manualmente in quanto le estensioni al modello di dati non sono supportate da Entity Designer. Per ulteriori informazioni sul file con estensione edmx generato dagli strumenti di Entity Data Model, vedere [Cenni preliminari sui file con estensione edmx (Entity Framework)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)). Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono creati al completamento della [WCF Data Services avvio rapido](quickstart-wcf-data-services.md).  
  
### <a name="to-manually-modify-the-northwindedmx-file-to-add-feed-customization-attributes"></a>Per modificare manualmente il file Northwind.edmx per aggiungere attributi di personalizzazione dei feed  
  
1. In **Esplora soluzioni**fare clic con il pulsante `Northwind.edmx` destro del mouse sul file, quindi scegliere **Apri con**.  
  
2. Nella finestra di dialogo **Apri con-Northwind. edmx** selezionare **editor XML**, quindi fare clic su **OK**.  
  
3. Individuare l'elemento `ConceptualModels` e sostituire il tipo di entità `Customers` esistente con l'elemento seguente che contiene gli attributi per il mapping della personalizzazione dei feed:  
  
     [!code-xml[Astoria Custom Feeds#EdmFeedCustomers](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/northwind.csdl#edmfeedcustomers)]  
  
4. Salvare le modifiche e chiudere il file Northwind.edmx.  
  
5. Opzionale Fare clic con il pulsante destro del mouse sul file Northwind. edmx, quindi scegliere **Esegui strumento personalizzato**.  
  
     Il file del livello di oggetti verrà rigenerato, poiché potrebbe essere necessario.  
  
6. Ricompilare il progetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio precedente per l'URI `http://myservice/Northwind.svc/Customers('ALFKI')` viene restituito il risultato seguente.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/edmfeedresult.xml#edmfeedresult)]  
  
## <a name="see-also"></a>Vedere anche

- [Provider di Entity Framework](entity-framework-provider-wcf-data-services.md)
