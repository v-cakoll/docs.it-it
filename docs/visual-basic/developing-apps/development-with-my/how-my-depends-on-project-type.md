---
title: Dipendenza di My dal tipo di progetto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 72b9799d1f5ba7efa37d5f8f2a633e6806a58607
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2019
ms.locfileid: "63808076"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Dipendenza di My dal tipo di progetto (Visual Basic)
`My` espone solo gli oggetti richiesti da un particolare tipo di progetto. Ad esempio, il `My.Forms` oggetto è disponibile in un'applicazione Windows Forms, ma non è disponibile in un'applicazione console. Questo argomento viene illustrato che `My` gli oggetti sono disponibili in diversi tipi di progetto.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Il Windows in applicazioni e siti Web  
 `My` espone solo gli oggetti che sono utili per il tipo di progetto corrente. Elimina gli oggetti che non sono applicabili. Ad esempio, l'immagine seguente mostra il `My` modello a oggetti in un progetto Windows Form.  
  
 ![Diagramma che mostra il modello a oggetti My in un'applicazione Windows Form.](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 In un progetto di sito Web `My` espone gli oggetti che sono rilevanti per gli sviluppatori Web (ad esempio il `My.Request` e `My.Response` oggetti), eliminando gli oggetti che non sono rilevanti (, ad esempio il `My.Forms` oggetto). La figura seguente mostra il `My` modello a oggetti in un progetto sito Web:  
  
 ![Diagramma che mostra il modello a oggetti My in un'applicazione Web.](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>Dettagli progetto  
 La tabella seguente illustra che `My` gli oggetti sono abilitati per impostazione predefinita per otto tipi di progetto: Applicazione Windows, libreria di classi, applicazione console, Windows libreria di controlli, Web libreria di controlli, Windows service, vuoto e sito Web.  
  
 Sono disponibili tre versioni del `My.Application` object, due versioni del `My.Computer` oggetto e due versioni di `My.User` ; dell'oggetto dettagli su queste versioni sono disponibili nelle note dopo la tabella.  
  
|Oggetto My|Applicazione Windows|Libreria di classi|Applicazione console|Libreria di controlli Windows|Libreria di controlli Web|Servizio Windows|Empty|Sito Web|  
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
  
 <sup>1</sup> versione di Windows Form di `My.Application`. Deriva dalla versione della console (vedere nota 3) Aggiunge il supporto per l'interazione con le finestre dell'applicazione e fornisce il modello di applicazione Visual Basic.  
  
 <sup>2</sup> versione della libreria `My.Application`. Fornisce la funzionalità di base necessaria a un'applicazione: fornisce i membri per la scrittura nel registro dell'applicazione e l'accesso alle informazioni dell'applicazione.  
  
 <sup>3</sup> versione della console di `My.Application`. Deriva dalla versione della libreria (vedere nota 2), e aggiunge membri aggiuntivi per l'accesso gli argomenti della riga di comando e informazioni sulla distribuzione ClickOnce dell'applicazione.  
  
 <sup>4</sup> versione di Windows di `My.Computer`. Deriva dalla versione del Server (vedere nota 5) e fornisce l'accesso a oggetti utili in un computer client, ad esempio la tastiera, schermo e del mouse.  
  
 <sup>5</sup> versione del server `My.Computer`. Fornisce informazioni di base relative al computer, ad esempio il nome, l'accesso per l'orologio e così via.  
  
 <sup>6</sup> versione di Windows di `My.User`. Questo oggetto è associato l'identità del thread corrente.  
  
 <sup>7</sup> versione web della `My.User`. Questo oggetto è associato l'identità dell'utente della richiesta HTTP corrente dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Personalizzazione degli oggetti disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Oggetto My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
- [Oggetto My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)
- [Oggetto My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
