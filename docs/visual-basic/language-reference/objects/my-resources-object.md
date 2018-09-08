---
title: Oggetto My (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 41b6eaa39abfab6cda943162c5c10d1cbeaa9e49
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44186565"
---
# <a name="myresources-object"></a>Oggetto My.Resources
Fornisce proprietà e classi per l'accesso alle risorse dell'applicazione.  
  
## <a name="remarks"></a>Note  
 Il `My.Resources` oggetto consente di accedere alle risorse dell'applicazione e consente in modo dinamico di recuperare le risorse per l'applicazione. Per altre informazioni, vedere [gestione delle applicazioni alle risorse (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 Il `My.Resources` oggetto espone solo le risorse globali. Non fornisce accesso ai file di risorse associati ai form. È necessario accedere alle risorse form dal form.  
  
 È possibile accedere i file di risorse specifiche delle impostazioni cultura dell'applicazione dal `My.Resources` oggetto. Per impostazione predefinita, il `My.Resources` oggetto cerca le risorse dal file di risorse che corrisponde alla lingua nel <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> proprietà. Tuttavia, è possibile eseguire l'override di questo comportamento e specificare determinate impostazioni cultura da utilizzare per le risorse. Per altre informazioni, vedere [Risorse nelle applicazioni desktop](../../../framework/resources/index.md).  
  
## <a name="properties"></a>Proprietà  
 Le proprietà del `My.Resources` oggetto forniscono accesso in lettura alle risorse dell'applicazione. Per aggiungere o rimuovere le risorse, usare il **Progettazione progetti**. È possibile accedere alle risorse aggiunte tramite il **creazione progetti** usando `My.Resources.``resourceName`.  
  
 È anche possibile aggiungere o rimuovere i file di risorse, selezionare il progetto in **Esplora soluzioni** e facendo clic su **Aggiungi nuovo elemento** oppure **Aggiungi elemento esistente** dal  **Progetto** menu. È possibile accedere alle risorse aggiunte in questo modo tramite `My.Resources.``resourceFileName`.`resourceName`.  
  
 Ogni risorsa ha un nome, categoria e valore, e queste impostazioni determinano come la proprietà per accedere alla risorsa viene visualizzata nel `My.Resources` oggetto. Per le risorse aggiunte nel **Progettazione progetti**:  
  
-   Il nome determina il nome della proprietà,  
  
-   I dati della risorsa sono il valore della proprietà,  
  
-   La categoria determina il tipo della proprietà:  
  
|Category|Tipo di dati proprietà|  
|---|---|  
|**Stringhe**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Immagini**|<xref:System.Drawing.Bitmap>|  
|**Icone**|<xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> Il <xref:System.IO.UnmanagedMemoryStream> deriva dalla classe la <xref:System.IO.Stream> classe, in modo che può essere utilizzato con i metodi che accettano i flussi, ad esempio il <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> (metodo).|  
|**File**|-   [Stringa](../../../visual-basic/language-reference/data-types/string-data-type.md) per file di testo.<br />-   <xref:System.Drawing.Bitmap> per i file di immagine.<br />-   <xref:System.Drawing.Icon> per i file di icona.<br />-   <xref:System.IO.UnmanagedMemoryStream> per i file audio.|  
|**Altro**|Determinata dalle informazioni nella finestra di progettazione **tipo** colonna.|  
  
## <a name="classes"></a>Classi  
 Il `My.Resources` oggetto espone ogni file di risorse come una classe con le proprietà condivise. Il nome della classe è identico al nome del file di risorse. Come descritto nella sezione precedente, le risorse in un file di risorse sono esposte come proprietà nella classe.  
  
## <a name="example"></a>Esempio  
 In questo esempio imposta il titolo di un form per la risorsa stringa denominata `Form1Title` nel file di risorse dell'applicazione. Per l'esempio funzioni, l'applicazione deve avere una stringa denominata `Form1Title` nel relativo file di risorse.  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a>Esempio  
 In questo esempio imposta l'icona del form per l'icona denominato `Form1Icon` che viene archiviato nel file di risorse dell'applicazione. Affinché l'esempio funzioni, l'applicazione deve contenere un'icona denominata `Form1Icon` nel relativo file di risorse.  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a>Esempio  
 In questo esempio imposta l'immagine di sfondo di un form per la risorsa di immagine denominata `Form1Background`, ovvero in file di risorse dell'applicazione. Per questo esempio funzioni, l'applicazione deve avere una risorsa immagine denominata `Form1Background` nel relativo file di risorse.  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a>Esempio  
 In questo esempio riproduce il suono archiviata come una risorsa audio denominata `Form1Greeting` nel file di risorse dell'applicazione. Per l'esempio funzioni, l'applicazione deve avere una risorsa audio denominata `Form1Greeting` nel relativo file di risorse. Il `My.Computer.Audio.Play` metodo è disponibile solo per le applicazioni Windows Form.  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a>Esempio  
 In questo esempio recupera la versione in lingua francese di una risorsa di stringa dell'applicazione. La risorsa è denominata `Message`. Per modificare le impostazioni cultura che il `My.Resources` utilizzata dall'oggetto, l'esempio Usa <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 Per questo esempio funzioni, l'applicazione deve avere una stringa denominata `Message` nella relativa risorsa file e l'applicazione devono avere la versione in lingua francese del file di risorse, Resources.fr-FR. resx. Se l'applicazione non ha la versione in lingua francese del file di risorse, il `My.Resource` oggetto recupera le risorse dal file di risorse di impostazioni cultura predefinite.  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione delle risorse delle applicazioni (.NET)](/visualstudio/ide/managing-application-resources-dotnet)  
 [Risorse nelle applicazioni desktop](../../../framework/resources/index.md)  

