---
title: Esempio di tecnologia per la serializzazione di generics dei servizi Web
ms.date: 03/30/2017
ms.assetid: cdc15ea4-f678-4729-8ebe-188ae720bef7
ms.openlocfilehash: 467bfe1fd9eb8a0222385c34cb29a90df00dc937
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960756"
---
# <a name="web-services-generics-serialization-technology-sample"></a>Esempio di tecnologia per la serializzazione di generics dei servizi Web
[Scarica esempio](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/GenericsSerialization.zip.exe)  
  
 In questo esempio viene illustrato come utilizzare e controllare la serializzazione di generics nei servizi Web ASP.NET.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Per compilare l'esempio utilizzando Visual Studio  
  
1. Aprire Visual Studio e scegliere **Nuovo sito Web** dal menu **File**.  
  
2. Nel riquadro sinistro della finestra di dialogo **Nuovo sito Web** scegliere il linguaggio di programmazione desiderato e quindi nel riquadro destro selezionare **Servizio Web ASP.NET**.  
  
3. Fare clic su **Sfoglia** e passare alla sottodirectory \CS\GenericsService.  
  
4. Selezionare il file Service.asmx per aprirlo in Visual Studio.  
  
5. Nel menu **Compila** scegliere **Compila soluzione**.  
  
> [!NOTE]
> I primi cinque passaggi di questo elenco sono facoltativi. Il runtime di .NET Framework genererà automaticamente il servizio Web la prima volta che verrà richiesto.  
  
> [!NOTE]
> Di seguito sono indicati i passaggi necessari per compilare l'esempio.  
  
1. Aprire Esplora file e passare alla sottodirectory nella \CS..  
  
2. Fare clic con il pulsante destro del mouse sull'icona della sottodirectory GenericsService e quindi scegliere **Condivisione e sicurezza**.  
  
3. Nella scheda **Condivisione Web** selezionare **Condividi questa cartella**.  
  
> [!IMPORTANT]
> Prendere nota del nome della directory virtuale indicato nel riquadro **Alias** in quanto servirà per eseguire l'esempio.  
  
### <a name="to-build-the-sample-using-internet-information-services"></a>Per compilare l'esempio utilizzando Internet Information Services  
  
1. Aprire lo snap-in di gestione **Internet Information Services** ed espandere **Siti Web**.  
  
2. Fare clic su **Sito Web predefinito**, selezionare **Nuovo** e quindi selezionare **Directory virtuale** per avviare la **Creazione guidata Directory virtuale**.  
  
3. Fare clic su **Avanti**, immettere l'alias pubblico per la directory virtuale e fare clic su **Avanti**.  
  
4. Immettere il percorso della directory in cui è stato salvato l'esempio (generalmente la sottodirectory \CS\GenericsService) e fare clic su **Avanti**. Fare clic su **Avanti** per uscire dalla procedura guidata.  
  
> [!IMPORTANT]
> Prendere nota del nome della directory virtuale indicato nel riquadro **Alias** in quanto servirà per eseguire l'esempio.  
  
### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1. Aprire una finestra del browser, quindi fare clic sulla barra degli indirizzi.  
  
2. Digitare `http://localhost/[virtual directory]/Service.asmx`, dove `[virtual directory]` rappresenta la directory virtuale creata durante la compilazione dell'esempio.  
  
## <a name="remarks"></a>Osservazioni  
 Nell'esempio viene visualizzata una pagina ASP.NET predefinita che contiene collegamenti alla definizione del servizio Web. Oltre a modificare il codice sorgente per il servizio Web, è possibile personalizzare la visualizzazione. Per altre informazioni, vedere [Compilazione di client dei servizi Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w3h45ebk(v=vs.100)).  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Collections.Generic>
- <xref:System.Web.Services>
- <xref:System.Xml.Serialization>
- [Serializzazione](../../../docs/standard/serialization/index.md)
- [Servizi Web XML creati mediante ASP.NET e tramite client di servizi Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))
