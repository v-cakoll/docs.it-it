---
title: Risoluzione delle risorse esterne durante l'elaborazione XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 3a59d31c-0ec5-4de6-a2a9-558531c8116e
ms.openlocfilehash: 58407d5f0c6e602af15f5b19b9a19cc6379b9af7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710284"
---
# <a name="resolving-external-resources-during-xslt-processing"></a>Risoluzione delle risorse esterne durante l'elaborazione XSLT
Durante una trasformazione XSLT si presentano vari casi in cui può essere necessario risolvere le risorse esterne.  
  
## <a name="using-the-xmlresolver-class"></a>Utilizzo della classe XmlResolver  
 La classe <xref:System.Xml.XmlResolver> viene usata per risolvere risorse esterne. Nella tabella seguente vengono descritti i casi in cui il tipo <xref:System.Xml.XmlResolver> viene interessato dall'elaborazione XSLT.  
  
|Attività XSLT|Scopo per il quale viene usato XmlResolver|  
|---------------|--------------------------------------|  
|Compilare il foglio di stile.|Risolvere l'URI del foglio di stile.<br /><br /> e<br /><br /> Risolvere i riferimenti URI negli elementi `xsl:import` o `xsl:include`.|  
|Eseguire il foglio di stile.|Risolvere l'URI del documento di contesto.<br /><br /> e<br /><br /> Risolvere i riferimenti URI in qualsiasi funzione `document()` XSLT.|  
  
 I metodi <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> e <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> includono overload che accettano un oggetto <xref:System.Xml.XmlResolver> come argomento. Se non viene specificato alcun tipo <xref:System.Xml.XmlResolver>, viene usato un tipo predefinito <xref:System.Xml.XmlUrlResolver> senza credenziali.  
  
 Nell'elenco seguente viene descritto quando può essere necessario specificare un oggetto <xref:System.Xml.XmlResolver>:  
  
- Se il processo XSLT richiede l'accesso a una risorsa di rete che richiede l'autenticazione, è possibile usare un tipo <xref:System.Xml.XmlResolver> con le credenziali necessarie.  
  
- Se si desidera limitare le risorse a cui può accedere il processo XSLT, è possibile usare un <xref:System.Xml.XmlSecureResolver> con il set di autorizzazioni corretto. Usare la classe <xref:System.Xml.XmlSecureResolver> se è necessario aprire una risorsa che non si controlla o che non è considerata affidabile.  
  
- Se si desidera personalizzare il comportamento, è possibile implementare la propria classe <xref:System.Xml.XmlResolver> e usarla per risolvere le risorse.  
  
- Se si desidera assicurarsi che non venga eseguito l'accesso ad alcuna risorsa esterna, è possibile specificare `null` per l'argomento <xref:System.Xml.XmlResolver>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene compilato un foglio di stile archiviato su una risorsa di rete. Un oggetto <xref:System.Xml.XmlUrlResolver> specificherà le credenziali necessarie per accedere al foglio di stile.  
  
 [!code-csharp[XslCompiledTransform.Load#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Load/CS/Xslt_Load_v2.cs#11)]
 [!code-vb[XslCompiledTransform.Load#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Load/VB/Xslt_Load_v2.vb#11)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Xsl.XslCompiledTransform>
- <xref:System.Xml.Xsl.XsltSettings>
- [Trasformazioni XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
