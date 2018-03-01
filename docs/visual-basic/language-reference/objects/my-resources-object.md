---
title: Oggetto My.Resources
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 96e5b909d9945ed631cebe07e4cfc7d5dc2e019f
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="myresources-object"></a>Oggetto My.Resources
Fornisce proprietà e le classi per accedere alle risorse dell'applicazione.  
  
## <a name="remarks"></a>Note  
 Il `My.Resources` oggetto fornisce l'accesso alle risorse dell'applicazione e consente in modo dinamico le risorse di recuperare per l'applicazione. Per ulteriori informazioni, vedere [risorse dell'applicazione di gestione (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 Il `My.Resources` oggetto espone solo le risorse globali. Non fornisce accesso ai file di risorse associato al form. È necessario accedere alle risorse di modulo dal modulo.  
  
 È possibile accedere a file di risorse specifiche delle impostazioni cultura dell'applicazione dal `My.Resources` oggetto. Per impostazione predefinita, il `My.Resources` oggetto cerca le risorse dal file di risorse che corrisponde alle impostazioni cultura nel <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> proprietà. Tuttavia, è possibile eseguire l'override di questo comportamento e specificare determinate impostazioni cultura da utilizzare per le risorse. Per altre informazioni, vedere [Risorse nelle applicazioni desktop](../../../framework/resources/index.md).  
  
## <a name="properties"></a>Proprietà  
 Le proprietà del `My.Resources` oggetto fornire accesso in sola lettura alle risorse dell'applicazione. Per aggiungere o rimuovere risorse, utilizzare il **progettazione**. È possibile accedere alle risorse aggiunte mediante il **progettazione** utilizzando `My.Resources.``resourceName`.  
  
 È anche possibile aggiungere o rimuovere i file di risorse, selezionare il progetto in **Esplora** e facendo clic su **Aggiungi nuovo elemento** o **Aggiungi elemento esistente** dal  **Progetto** menu. È possibile accedere alle risorse aggiunte in questo modo tramite `My.Resources.``resourceFileName`.`resourceName`.  
  
 Ogni risorsa ha un nome, categoria e valore, e queste impostazioni determinano l'aspetto delle proprietà per accedere alla risorsa nel `My.Resources` oggetto. Per le risorse aggiunte nel **progettazione**:  
  
-   Il nome determina il nome della proprietà,  
  
-   I dati delle risorse sono il valore della proprietà,  
  
-   La categoria determina il tipo della proprietà:  
  
|Category|Tipo di dati di proprietà|  
|---|---|  
|**Stringhe**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Immagini**|<xref:System.Drawing.Bitmap>|  
|**Icone**|<xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> Il <xref:System.IO.UnmanagedMemoryStream> deriva dalla classe di <xref:System.IO.Stream> classe può essere utilizzato con metodi che accettano flussi, ad esempio il <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> (metodo).|  
|**File**|-   [Stringa](../../../visual-basic/language-reference/data-types/string-data-type.md) per file di testo.<br />-   <xref:System.Drawing.Bitmap>file di immagine.<br />-   <xref:System.Drawing.Icon>per i file di icona.<br />-   <xref:System.IO.UnmanagedMemoryStream>per i file audio.|  
|**Altro**|Determinata dalle informazioni nella finestra di progettazione **tipo** colonna.|  
  
## <a name="classes"></a>Classi  
 Il `My.Resources` oggetto espone ogni file di risorse come una classe con le proprietà condivise. Il nome della classe è identico al nome del file di risorse. Come descritto nella sezione precedente, le risorse in un file di risorse sono esposte come proprietà nella classe.  
  
## <a name="example"></a>Esempio  
 In questo esempio imposta il titolo di un form per la risorsa di stringa denominata `Form1Title` nel file di risorse dell'applicazione. Per eseguire l'esempio, l'applicazione deve avere una stringa denominata `Form1Title` nel relativo file di risorse.  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a>Esempio  
 In questo esempio imposta l'icona del form per l'icona denominato `Form1Icon` che viene archiviato nel file di risorse dell'applicazione. Per eseguire l'esempio, l'applicazione deve avere un'icona denominata `Form1Icon` nel relativo file di risorse.  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a>Esempio  
 In questo esempio imposta l'immagine di sfondo di un form per la risorsa immagine denominata `Form1Background`, ovvero nel file di risorse dell'applicazione. Per eseguire questo esempio, l'applicazione deve avere una risorsa immagine denominata `Form1Background` nel relativo file di risorse.  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a>Esempio  
 In questo esempio riproduce il suono che viene archiviato come una risorsa audio denominata `Form1Greeting` nel file di risorse dell'applicazione. Per eseguire l'esempio, l'applicazione deve contenere una risorsa audio denominata `Form1Greeting` nel relativo file di risorse. Il `My.Computer.Audio.Play` metodo è disponibile solo per le applicazioni Windows Form.  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a>Esempio  
 In questo esempio recupera la versione in lingua francese di una risorsa di stringa dell'applicazione. La risorsa è denominata `Message`. Per modificare le impostazioni cultura che il `My.Resources` oggetto utilizza, l'esempio Usa <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 Per eseguire questo esempio, l'applicazione deve avere una stringa denominata `Message` nella relativa risorsa file e l'applicazione devono avere la versione in lingua francese del file di risorse, ovvero Resources.fr-FR. resx. Se l'applicazione non ha la versione in lingua francese del file di risorse, il `My.Resource` oggetto recupera la risorsa dal file di risorse delle impostazioni cultura predefinite.  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione delle risorse delle applicazioni (.NET)](/visualstudio/ide/managing-application-resources-dotnet)  
 [Risorse nelle applicazioni desktop](../../../framework/resources/index.md)  

