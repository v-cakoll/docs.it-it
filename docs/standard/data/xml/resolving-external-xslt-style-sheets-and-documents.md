---
title: Risoluzione di fogli di stile e documenti XSLT esterni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 920cfe3b-d525-4bb2-abf6-9431651f9cf9
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a5e84935f9fff1f993a677d408287cd775269f03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="resolving-external-xslt-style-sheets-and-documents"></a>Risoluzione di fogli di stile e documenti XSLT esterni
Durante una trasformazione si presentano vari casi in cui può essere necessario risolvere le risorse esterne.  
  
> [!NOTE]
>  La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 Durante una trasformazione si presentano vari casi in cui può essere necessario risolvere le risorse esterne:  
  
-   Durante l'esecuzione del metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> per individuare un foglio di stile esterno.  
  
-   Durante l'esecuzione del metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> per risolvere gli eventuali elementi `<xsl:include>` o `<xsl:import>` presenti nel foglio di stile.  
  
-   Durante l'esecuzione del metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> per risolvere eventuali funzioni `document()`.  
  
## <a name="using-the-xmlresolver-class"></a>Utilizzo della classe XmlResolver  
 Se per accedere a una risorsa di rete è richiesta l'autenticazione, usare i metodi <xref:System.Xml.Xsl.XslTransform.Load%2A> contenenti un parametro <xref:System.Xml.XmlResolver> per passare l'oggetto <xref:System.Xml.XmlResolver> che contiene il set di credenziali necessario.  
  
 Se si dispone di un oggetto <xref:System.Xml.XmlResolver> personalizzato che si desidera usare o se è necessario specificare credenziali diverse, occorre eseguire le attività riportate nella tabella seguente, che dipendono dal momento in cui è necessario risolvere la risorsa esterna.  
  
|Processo che richiede la risoluzione|Attività richiesta|  
|--------------------------------------|-------------------|  
|Durante l'esecuzione del metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> per individuare il foglio di stile.|Specificare il metodo di overload <xref:System.Xml.Xsl.XslTransform.Load%2A> che accetta come parametro il tipo <xref:System.Xml.XmlResolver>, qualora il foglio di stile si trovi in una risorsa che richiede credenziali.|  
|Durante l'esecuzione del metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> per risolvere `<xsl:include>` o `<xsl:import>`.|Specificare il metodo di overload <xref:System.Xml.Xsl.XslTransform.Load%2A> che accetta come parametro un tipo <xref:System.Xml.XmlResolver>. Il tipo <xref:System.Xml.XmlResolver> viene usato per caricare i fogli di stile a cui fa riferimento l'istruzione `import` o `include`. Se viene passato il valore `null`, le risorse esterne non vengono risolte.|  
|Durante una trasformazione per risolvere eventuali funzioni `document()`.|Specificare il <xref:System.Xml.XmlResolver> durante la trasformazione usando il <xref:System.Xml.Xsl.XslTransform.Transform%2A> metodo che accetta un <xref:System.Xml.XmlResolver> argomento.|  
  
 Il `document()` funzione recupera le altre risorse XML da un foglio di stile inoltre ai dati XML iniziali forniti dal flusso di input. Poiché questa funzione consente di includere i dati XML che si trovano in altre posizioni, se al metodo <xref:System.Xml.XmlResolver> viene fornito un tipo `null` con valore <xref:System.Xml.Xsl.XslTransform.Transform%2A>, la funzione `document()` non può essere eseguita. Se si desidera usare la funzione `document()`, usare il metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> che accetta un tipo <xref:System.Xml.XmlResolver> come parametro, oltre a impostare il set di autorizzazioni appropriato.  
  
 Per altre informazioni sul metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> e sul relativo uso del tipo <xref:System.Xml.XmlResolver>, vedere il metodo <xref:System.Xml.Xsl.XslTransform.Load%28System.String%2CSystem.Xml.XmlResolver%29?displayProperty=nameWithType>.  
  
 Quando viene chiamato il metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>, le autorizzazioni vengono calcolate in base all'evidenza fornita in fase di caricamento e il set di autorizzazioni viene assegnato all'intero processo di trasformazione. Se la funzione `document()` tenta di avviare un'azione che richiede autorizzazioni non presenti nel set, viene generata un'eccezione.  
  
## <a name="see-also"></a>Vedere anche  
 [Trasformazioni XSLT con la classe XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [Classe XslTransform implementa il processore XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [Output da un XslTransform](../../../../docs/standard/data/xml/outputs-from-an-xsltransform.md)  
 [Trasformazioni XSLT su diversi archivi](../../../../docs/standard/data/xml/xslt-transformations-over-different-stores.md)  
 [XsltArgumentList per i parametri dei fogli di stile e gli oggetti di estensione](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md)  
 [XSLT Stylesheet Scripting utilizzando \<msxsl: script >](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md)  
 [Supporto per la funzione msxsl](../../../../docs/standard/data/xml/support-for-the-msxsl-node-set-function.md)  
 [XPathNavigator nelle trasformazioni](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [XPathNodeIterator nelle trasformazioni](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [Input di XPathDocument in XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [Input di XmlDataDocument in XslTransform](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)  
 [Input di XmlDocument in XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
