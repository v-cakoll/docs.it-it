---
title: Utilizzo della classe XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: 8705b4c6324ce20a1f37d3ee864ab494adcdd6a5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281770"
---
# <a name="using-the-xslcompiledtransform-class"></a>Utilizzo della classe XslCompiledTransform
La classe <xref:System.Xml.Xsl.XslCompiledTransform> è il processore XSLT di Microsoft .NET Framework. Questa classe consente di compilare fogli di stile e di eseguire trasformazioni XSLT.  
  
> [!NOTE]
> Sebbene le prestazioni complessive della classe <xref:System.Xml.Xsl.XslCompiledTransform> siano migliori rispetto alla classe <xref:System.Xml.Xsl.XslTransform>, l'esecuzione del metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> della classe <xref:System.Xml.Xsl.XslCompiledTransform> potrebbe risultare più lenta di quella del metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> della classe <xref:System.Xml.Xsl.XslTransform> la prima volta che tale metodo viene chiamato su una trasformazione. Questa situazione si verifica perché il file XSLT deve essere compilato prima del caricamento. Per altre informazioni, vedere il post di blog seguente: [XslCompiledTransform Slower than XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform) (XslCompiledTransform è più lento di XslTransform?)  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Input alla classe XslCompiledTransform](inputs-to-the-xslcompiledtransform-class.md)  
 Vengono descritte le opzioni di input XSLT disponibili.  
  
 [Opzioni di output nella classe XslCompiledTransform](output-options-on-the-xslcompiledtransform-class.md)  
 Vengono descritte le opzioni di output XSLT disponibili.  
  
 [Risoluzione delle risorse esterne durante l'elaborazione XSLT](resolving-external-resources-during-xslt-processing.md)  
 Viene descritto come usare la classe <xref:System.Xml.XmlResolver> per risolvere risorse esterne.  
  
 [Estensione di fogli di stile XSLT](extending-xslt-style-sheets.md)  
 Viene descritto il supporto delle estensioni XSLT.  
  
|||  
|-|-|  
|[Errori XSLT risolvibili](recoverable-xslt-errors.md)|Vengono elencati i comportamenti discretionary consentiti dalla raccomandazione W3C (World Wide Web Consortium) XSLT 1.0 e viene descritto il modo in cui tali comportamenti vengono gestiti dalla classe <xref:System.Xml.Xsl.XslCompiledTransform>.|  
|[Procedura: Trasformare un frammento di nodo](how-to-transform-a-node-fragment.md)|Viene descritto come trasformare un frammento di nodo.|  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Migrazione dalla classe XslTransform](migrating-from-the-xsltransform-class.md)  
 Viene descritto come migrare il codice dalla classe <xref:System.Xml.Xsl.XslTransform>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
