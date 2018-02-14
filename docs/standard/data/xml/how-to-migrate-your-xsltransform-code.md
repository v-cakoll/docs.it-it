---
title: 'Procedura: migrare il codice XslTransform'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 910beb2f-cfb3-4e8e-9936-f7e0c5f4064a
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9bfef535ecfae48ce09ef0eaca3f11de0a8d6667
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-migrate-your-xsltransform-code"></a>Procedura: migrare il codice XslTransform
Le nuove classi XSLT sono state progettate in modo analogo alle classi esistenti. La classe <xref:System.Xml.Xsl.XslCompiledTransform> sostituisce la classe <xref:System.Xml.Xsl.XslTransform>. I fogli di stile vengono compilati usando il metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>. Le trasformazioni vengono eseguite usando il metodo <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>. Nelle procedure seguenti vengono illustrate le attività comuni di XSLT e viene eseguito un confronto del codice usando la classe <xref:System.Xml.Xsl.XslTransform> e la classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
### <a name="to-transform-a-file-and-output-to-a-uri"></a>Per trasformare un file e un output in un URI  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#9](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#9)]
     [!code-vb[XML_Migration#9](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#9)]  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#10](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#10)]
     [!code-vb[XML_Migration#10](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#10)]  
  
### <a name="to-compile-a-style-sheet-and-use-a-resolver-with-default-credentials"></a>Per compilare un foglio di stile e usare un sistema di risoluzione con credenziali predefinite  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#11)]
     [!code-vb[XML_Migration#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#11)]  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#12](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#12)]
     [!code-vb[XML_Migration#12](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#12)]  
  
### <a name="to-use-an-xslt-parameter"></a>Per usare un parametro XSLT  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#13](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#13)]
     [!code-vb[XML_Migration#13](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#13)]  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#14](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#14)]
     [!code-vb[XML_Migration#14](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#14)]  
  
### <a name="to-enable-xslt-scripting"></a>Per abilitare lo script XSLT  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#15](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#15)]
     [!code-vb[XML_Migration#15](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#15)]  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
     [!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]  
  
### <a name="to-load-the-results-into-a-dom-object"></a>Per caricare i risultati in un oggetto DOM  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#19)]
     [!code-vb[XML_Migration#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#19)]  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
    > [!NOTE]
    >  La classe <xref:System.Xml.Xsl.XslCompiledTransform> non dispone di un metodo che restituisca i risultati della trasformazione XSLT come oggetto <xref:System.Xml.XmlReader>. Tuttavia, è possibile inviare l'output a un file XML e caricare quest'ultimo in un altro oggetto.  
  
     [!code-csharp[XML_Migration#20](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#20)]
     [!code-vb[XML_Migration#20](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#20)]  
  
### <a name="to-stream-the-results-into-another-data-store"></a>Per inviare il flusso dei risultati a un altro archivio dati  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#17](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#17)]
     [!code-vb[XML_Migration#17](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#17)]  
  
-   Codice che usa la classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#18](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#18)]
     [!code-vb[XML_Migration#18](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#18)]  
  
## <a name="see-also"></a>Vedere anche  
 [Migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 [Uso della classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
