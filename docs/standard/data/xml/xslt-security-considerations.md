---
title: Considerazioni sulla sicurezza XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: fea695be-617c-4977-9567-140e820436fc
ms.openlocfilehash: e6e490c0f637aace57dacc88ef49cc9be87532cd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709686"
---
# <a name="xslt-security-considerations"></a>Considerazioni sulla sicurezza XSLT
Il linguaggio XSLT dispone di un'ampia gamma di funzionalità che offrono notevoli prestazioni e flessibilità. Sono incluse numerose funzionalità utili che possono essere usate anche da origini esterne. Per usare XSLT senza problemi, è necessario comprendere i tipi di problemi di sicurezza che si possono verificare durante l'uso di XSLT e le strategie di base che è possibile applicare per limitare tali rischi.  
  
## <a name="xslt-extensions"></a>Estensioni XSLT  
 Due estensioni XSLT note sono gli script di fogli di stile e gli oggetti estensioni. Queste estensioni consentono al processore XSLT di eseguire il codice.  
  
- Gli oggetti estensioni consentono di aggiungere funzionalità di programmazione alle trasformazioni XSL.  
  
- Gli script possono essere incorporati nel foglio di stile usando l'elemento di estensione `msxsl:script`.  
  
### <a name="extension-objects"></a>Oggetti estensione  
 Gli oggetti estensione vengono aggiunti usando il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>. È richiesto il set di autorizzazioni FullTrust per supportare gli oggetti estensioni. In tal modo si assicura che non si verificherà un'elevazione delle autorizzazioni quando viene eseguito il codice dell'oggetto estensioni. Un tentativo di chiamata al metodo <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> senza le autorizzazioni FullTrust genererà un'eccezione di sicurezza.  
  
### <a name="style-sheet-scripts"></a>Script di foglio di stile  
 Gli script possono essere incorporati in un foglio di stile usando l'elemento di estensione `msxsl:script`. Il supporto degli script è una funzionalità opzionale della classe <xref:System.Xml.Xsl.XslCompiledTransform> e per impostazione predefinita è disabilitata. È possibile abilitare l'inserimento di script impostando la proprietà <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A?displayProperty=nameWithType> su `true` e passando l'oggetto <xref:System.Xml.Xsl.XsltSettings> al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.  
  
#### <a name="guidelines"></a>Indicazioni  
 Abilitare l'inserimento di script solo se il foglio di stile proviene da un'origine attendibile. Se non è possibile verificare l'origine del foglio di stile o se il foglio di stile non deriva da un'origine attendibile, passarlo in `null` per l'argomento delle impostazioni XSLT.  
  
## <a name="external-resources"></a>Risorse esterne  
 Il linguaggio XSLT dispone di funzioni come `xsl:import`, `xsl:include` o `document()`, dove il processore deve risolvere riferimenti all'URI. La classe <xref:System.Xml.XmlResolver> viene usata per risolvere risorse esterne. Può essere necessario risolvere le risorse esterne nei seguenti due casi:  
  
- Quando si compila un foglio di stile, viene usato il tipo <xref:System.Xml.XmlResolver> per la risoluzione di `xsl:import` e `xsl:include`.  
  
- Quando si esegue la trasformazione, viene usato il tipo <xref:System.Xml.XmlResolver> per risolvere la funzione `document()`.  
  
    > [!NOTE]
    > Per impostazione predefinita, la funzione `document()` è disabilitata nella classe <xref:System.Xml.Xsl.XslCompiledTransform>. È possibile abilitare la funzione impostando la proprietà <xref:System.Xml.Xsl.XsltSettings.EnableDocumentFunction%2A?displayProperty=nameWithType> su `true` e passando l'oggetto <xref:System.Xml.Xsl.XsltSettings> al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.  
  
 I metodi <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> e <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> includono ciascuno overload che accettano un tipo <xref:System.Xml.XmlResolver> come argomento. Se non viene specificato alcun tipo <xref:System.Xml.XmlResolver>, viene usato un tipo predefinito <xref:System.Xml.XmlUrlResolver> senza credenziali.  
  
#### <a name="guidelines"></a>Indicazioni  
 Abilitare la funzione `document()` solo se il foglio di stile proviene da un'origine attendibile.  
  
 Nell'elenco seguente viene descritto quando può essere necessario specificare un oggetto <xref:System.Xml.XmlResolver>:  
  
- Se il processo XSLT richiede l'accesso a una risorsa di rete che richiede l'autenticazione, è possibile usare un tipo <xref:System.Xml.XmlResolver> con le credenziali necessarie.  
  
- Se si desidera limitare le risorse a cui può accedere il processo XSLT, è possibile usare un <xref:System.Xml.XmlSecureResolver> con il set di autorizzazioni corretto. Usare la classe <xref:System.Xml.XmlSecureResolver> se è necessario aprire una risorsa che non si controlla o che non è considerata affidabile.  
  
- Se si desidera personalizzare il comportamento, è possibile implementare la propria classe <xref:System.Xml.XmlResolver> e usarla per risolvere le risorse.  
  
- Se si desidera assicurarsi che non venga eseguito l'accesso ad alcuna risorsa esterna, è possibile specificare `null` per l'argomento <xref:System.Xml.XmlResolver>.  
  
## <a name="see-also"></a>Vedi anche

- [Trasformazioni XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
- [Risoluzione delle risorse esterne durante l'elaborazione XSLT](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)
- [Sicurezza dall'accesso di codice](../../../../docs/framework/misc/code-access-security.md)
