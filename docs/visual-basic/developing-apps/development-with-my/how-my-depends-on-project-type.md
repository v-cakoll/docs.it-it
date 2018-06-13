---
title: Dipendenza di My dal tipo di progetto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: d196309bb2780db757515bd6ba1927c5821e2475
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33592080"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Dipendenza di My dal tipo di progetto (Visual Basic)
`My` espone solo gli oggetti richiesti da un particolare tipo di progetto. Ad esempio, il `My.Forms` oggetto è disponibile in un'applicazione Windows Form ma non è disponibile in un'applicazione console. Questo argomento viene illustrato che `My` gli oggetti sono disponibili in diversi tipi di progetto.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>In Windows le applicazioni e siti Web  
 `My` espone solo gli oggetti che sono utili per il tipo di progetto corrente. esso Elimina gli oggetti che non sono applicabili. Ad esempio, la figura seguente mostra il `My` modello a oggetti in un progetto Windows Form.  
  
 ![Forma di My in un'applicazione Windows Forms](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 In un progetto di sito Web, `My` espone gli oggetti che sono rilevanti per gli sviluppatori Web (ad esempio il `My.Request` e `My.Response` oggetti), eliminando gli oggetti che non sono rilevanti (ad esempio il `My.Forms` oggetto). La figura seguente mostra il `My` modello a oggetti in un progetto di sito Web:  
  
 ![Forma di My in un'applicazione Web](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## <a name="project-details"></a>Dettagli di progetto  
 Nella tabella seguente viene illustrato che `My` gli oggetti sono abilitati per impostazione predefinita per otto tipi di progetti: applicazione Windows, libreria di classi, applicazione console, libreria di controlli Windows, libreria di controlli Web, servizio Windows, vuoto e sito Web.  
  
 Sono disponibili tre versioni del `My.Application` oggetto, due versioni del `My.Computer` oggetto e due versioni di `My.User` ; dell'oggetto informazioni dettagliate su queste versioni vengono fornite nel piè di pagina dopo la tabella.  
  
|My (oggetto)|Applicazione Windows|Libreria di classi|Applicazione console|Libreria di controlli Windows|Libreria di controlli Web|Servizio Windows|Empty|Sito Web|  
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
  
 <sup>1</sup> versione di Windows Form di `My.Application`. Deriva la versione della console (vedere nota 3); Aggiunge il supporto per l'interazione con le finestre dell'applicazione e fornisce il modello di applicazione Visual Basic.  
  
 <sup>2</sup> versione della libreria `My.Application`. Fornisce la funzionalità di base necessaria a un'applicazione: fornisce i membri per l'accesso a informazioni sull'applicazione e la scrittura nel registro applicazioni.  
  
 <sup>3</sup> versione della console di `My.Application`. Deriva dalla versione della libreria (vedere nota 2), e aggiunge membri aggiuntivi per l'accesso ad argomenti della riga di comando dell'applicazione e informazioni sulla distribuzione di ClickOnce.  
  
 <sup>4</sup> versione di Windows di `My.Computer`. Deriva la versione del Server (vedere nota 5) e fornisce l'accesso a oggetti utili in un computer client, ad esempio la tastiera, una schermata e un mouse.  
  
 <sup>5</sup> versione del server `My.Computer`. Fornisce informazioni di base relative al computer, ad esempio il nome, l'accesso per l'orologio e così via.  
  
 <sup>6</sup> versione di Windows di `My.User`. Questo oggetto è associato all'identità corrente del thread.  
  
 <sup>7</sup> versione web di `My.User`. Questo oggetto è associato l'identità dell'utente della richiesta HTTP corrente dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.Logging.Log>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [Personalizzazione degli oggetti disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [Oggetto My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)  
 [Oggetto My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)  
 [Oggetto My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
