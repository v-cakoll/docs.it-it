---
title: Dipendenza di My dal tipo di progetto
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 740185d8030c09e8813bc7680b451f6326588593
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411714"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Dipendenza di My dal tipo di progetto (Visual Basic)

`My`espone solo gli oggetti richiesti da un determinato tipo di progetto. Ad esempio, l' `My.Forms` oggetto è disponibile in un Windows Forms Application ma non è disponibile in un'applicazione console. In questo argomento vengono descritti `My` gli oggetti disponibili in diversi tipi di progetto.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>My in siti Web e applicazioni Windows  

 `My`espone solo gli oggetti utili nel tipo di progetto corrente. Elimina gli oggetti non applicabili. Nell'immagine seguente, ad esempio, viene illustrato il `My` modello a oggetti in un progetto Windows Forms.  
  
 ![Diagramma che mostra il modello a oggetti in un Windows Forms Application.](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 In un progetto di sito Web, `My` espone oggetti rilevanti per uno sviluppatore web (ad esempio, gli `My.Request` `My.Response` oggetti e) durante l'eliminazione degli oggetti che non sono rilevanti, ad esempio l' `My.Forms` oggetto. Nell'immagine seguente viene illustrato il `My` modello a oggetti in un progetto di sito Web:  
  
 ![Diagramma che mostra il modello a oggetti My in un'applicazione Web.](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>Dettagli progetto  

 La tabella seguente mostra `My` gli oggetti abilitati per impostazione predefinita per otto tipi di progetto: applicazione Windows, libreria di classi, applicazione console, libreria di controlli Windows, libreria di controlli Web, servizio Windows, vuoto e sito Web.  
  
 Sono disponibili tre versioni dell' `My.Application` oggetto, due versioni dell' `My.Computer` oggetto e due versioni dell'oggetto. le `My.User` informazioni dettagliate su queste versioni vengono fornite nelle note a piè di pagina dopo la tabella.  
  
|Oggetto My|Applicazione Windows|Libreria di classi|Applicazione console|Libreria di controlli Windows|Libreria di controlli Web|Servizio Windows|Vuoto|Sito Web|  
|---|---|---|---|---|---|---|---|---|  
|`My.Application`|**Sì** <sup>1</sup>|**Sì** <sup>2</sup>|**Sì** <sup>3</sup>|**Sì** <sup>2</sup>|No|**Sì** <sup>3</sup>|No|No|  
|`My.Computer`|**Sì** <sup>4</sup>|**Sì** <sup>4</sup>|**Sì** <sup>4</sup>|**Sì** <sup>4</sup>|**Sì** <sup>5</sup>|**Sì** <sup>4</sup>|No|**Sì** <sup>5</sup>|  
|`My.Forms`|**Sì**|No|No|**Sì**|No|No|No|No|  
|`My.Log`|No|No|No|No|No|No|No|**Sì**|  
|`My.Request`|No|No|No|No|No|No|No|**Sì**|  
|`My.Resources`|**Sì**|**Sì**|**Sì**|**Sì**|**Sì**|**Sì**|No|No|  
|`My.Response`|No|No|No|No|No|No|No|**Sì**|  
|`My.Settings`|**Sì**|**Sì**|**Sì**|**Sì**|**Sì**|**Sì**|No|No|  
|`My.User`|**Sì** <sup>6</sup>|**Sì** <sup>6</sup>|**Sì** <sup>6</sup>|**Sì** <sup>6</sup>|**Sì** <sup>7</sup>|**Sì** <sup>6</sup>|No|**Sì** <sup>7</sup>|  
|`My.WebServices`|**Sì**|**Sì**|**Sì**|**Sì**|**Sì**|**Sì**|No|No|  
  
 <sup>1</sup> Windows Forms versione di `My.Application` . Deriva dalla versione della console (vedere la nota 3); aggiunge il supporto per l'interazione con le finestre dell'applicazione e fornisce il modello di applicazione Visual Basic.  
  
 versione <sup>2</sup> della libreria `My.Application` . Fornisce le funzionalità di base necessarie per un'applicazione: fornisce i membri per la scrittura nel registro applicazioni e l'accesso alle informazioni sull'applicazione.  
  
 <sup>3</sup> versione della console di `My.Application` . Deriva dalla versione della libreria (vedere la nota 2) e aggiunge membri aggiuntivi per accedere agli argomenti della riga di comando dell'applicazione e alle informazioni sulla distribuzione ClickOnce.  
  
 <sup>4</sup> versione Windows di `My.Computer` . Deriva dalla versione del server (vedere la nota 5) e fornisce l'accesso a oggetti utili in un computer client, ad esempio la tastiera, lo schermo e il mouse.  
  
 versione di <sup>5</sup> server di `My.Computer` . Fornisce informazioni di base sul computer, ad esempio il nome, l'accesso al clock e così via.  
  
 <sup>6</sup> versione di Windows `My.User` . Questo oggetto è associato all'identità corrente del thread.  
  
 <sup>7</sup> versione Web di `My.User` . Questo oggetto è associato all'identità utente della richiesta HTTP corrente dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Personalizzazione degli oggetti disponibili in My](../customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Compilazione condizionale](../../programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../reference/command-line-compiler/define.md)
- [Oggetto My.Forms](../../language-reference/objects/my-forms-object.md)
- [Oggetto My.Request](../../language-reference/objects/my-request-object.md)
- [Oggetto My.Response](../../language-reference/objects/my-response-object.md)
- [Oggetto My.WebServices](../../language-reference/objects/my-webservices-object.md)
