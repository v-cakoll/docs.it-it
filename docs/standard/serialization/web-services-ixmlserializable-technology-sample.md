---
title: Esempio di tecnologia IXmlSerializable dei servizi Web
ms.date: 03/30/2017
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
ms.openlocfilehash: 343755c062fc13891d84131a5f7682e2e1466a5a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252792"
---
# <a name="web-services-ixmlserializable-technology-sample"></a>Esempio di tecnologia IXmlSerializable dei servizi Web
[Scaricare l'esempio](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 In questo esempio viene illustrato come utilizzare l'oggetto <xref:System.Xml.Serialization.IXmlSerializable> per controllare la serializzazione dei tipi personalizzati nei servizi Web ASP.NET.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Per compilare l'esempio utilizzando Visual Studio  
  
1.  Aprire [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] e selezionare **Nuovo sito Web** dal menu **File**.  
  
2.  Nel riquadro sinistro della finestra di dialogo **Nuovo sito Web** selezionare il linguaggio di programmazione desiderato e quindi nel riquadro destro selezionare **Servizio Web ASP.NET**.  
  
3.  Digitare **IXmlSerializable** come nome del nuovo servizio Web.  
  
4.  Nella finestra di Esplora soluzioni fare clic con il pulsante destro del mouse sull'icona relativa a Service.asmx e quindi scegliere **Elimina**. Ripetere questa operazione per il file code-behind Service.asmx.  
  
5.  Fare clic con il pulsante destro del mouse sulla directory del progetto e scegliere **Aggiungi elemento esistente**. Nella finestra di dialogo spostarsi nella sottodirectory Service della directory specifica del linguaggio.  
  
6.  Fare clic su Service.asmx, quindi ripetere questa operazione per il file code-behind Service.asmx.  
  
7.  Aprire [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], quindi spostarsi nella directory contenente la directory IXmlSerializable creata al passaggio 3 precedente.  
  
8.  Fare clic con il pulsante destro del mouse sull'icona relativa alla directory IXmlSerializable e scegliere **Condivisione e sicurezza**.  
  
9. Nella scheda Condivisione Web selezionare **Condividi questa cartella** e confermare le impostazioni predefinite, incluso il nome IXmlSerializable.  
  
10. Fare clic su **OK**.  
  
### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Aprire una finestra del browser, quindi fare clic sulla barra degli indirizzi.  
  
2.  Tipo di **http://localhost/IXmlSerializable/Service.asmx**.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Serialization.IXmlSerializable>  
- <xref:System.Xml.Serialization>  
- <xref:System.Xml.XmlConvert>  
- <xref:System.Xml.XmlQualifiedName>  
- <xref:System.Xml.XmlReader>  
- <xref:System.Xml.Schema.XmlSchema>  
- <xref:System.Xml.Schema.XmlSchemaSet>  
- <xref:System.Xml.XmlUrlResolver>  
- <xref:System.Xml.XmlWriter>
