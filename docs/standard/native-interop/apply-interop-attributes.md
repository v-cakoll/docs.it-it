---
title: Applicazione di attributi di interoperabilità
ms.date: 03/30/2017
helpviewer_keywords:
- design-time attributes
- .NET Framework, exposing components to COM
- attributes [.NET Framework], design-time functionality
- conversion-tool attributes
- attributes [.NET Framework], interop-specific
- attributes [.NET Framework], conversion-tool
- interoperation with unmanaged code, applying attributes
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
- COM interop, applying attributes
ms.assetid: b6014613-641c-4912-9e2f-83a99210a037
ms.openlocfilehash: ca104c512641774217de5e270dc50b7393fc5725
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159247"
---
# <a name="applying-interop-attributes"></a>Applicazione di attributi di interoperabilità
Lo spazio dei nomi <xref:System.Runtime.InteropServices> offre tre categorie di attributi specifici per l'interoperabilità: quelli applicati manualmente in fase di progettazione, quelli applicati dalle API e dagli strumenti di interoperabilità COM durante il processo di conversione e quelli applicati nell'uno o nell'altro modo.  
  
 Per informazioni su come applicare gli attributi nel codice gestito, vedere [Estensione di metadati mediante attributi](../../../docs/standard/attributes/index.md). Come per altri attributi personalizzati, è possibile applicare gli attributi specifici per l'interoperabilità a tipi, metodi, proprietà, parametri, campi e altri membri.  
  
## <a name="design-time-attributes"></a>Attributi della fase di progettazione  
 È possibile intervenire sul risultato del processo di conversione eseguito dalle API e dagli strumenti di interoperabilità COM usando gli attributi in fase di progettazione. La tabella seguente descrive gli attributi che è possibile applicare al codice sorgente gestito. Questi attributi possono essere applicati, in alcuni casi, anche dagli strumenti di interoperabilità COM.  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|<xref:System.Runtime.InteropServices.AutomationProxyAttribute>|Specifica se il marshalling del tipo deve essere effettuato mediante il gestore di marshalling di Automazione oppure un proxy e uno stub personalizzati.|  
|<xref:System.Runtime.InteropServices.ClassInterfaceAttribute>|Controlla il tipo di interfaccia generato per una classe.|  
|<xref:System.Runtime.InteropServices.CoClassAttribute>|Identifica il CLSID della coclasse originale importata da una libreria dei tipi.<br /><br /> Questo attributo viene in genere applicato dagli strumenti di interoperabilità COM.|  
|<xref:System.Runtime.InteropServices.ComImportAttribute>|Indica che è stata importata una definizione di interfaccia o una coclasse da una libreria dei tipi COM. Il runtime usa questo flag per determinare come attivare il tipo ed effettuarne il marshalling. Questo attributo impedisce la riesportazione del tipo in una libreria dei tipi.<br /><br /> Questo attributo viene in genere applicato dagli strumenti di interoperabilità COM.|  
|<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>|Indica che, quando l'assembly viene registrato per l'utilizzo da COM, deve essere chiamato un metodo per consentire l'esecuzione di codice utente durante il processo di registrazione.|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|Identifica le interfacce che sono fonti di eventi per la classe.<br /><br /> Questo attributo può essere applicato dagli strumenti di interoperabilità COM.|  
|<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>|Indica che, quando la registrazione dell'assembly da COM viene annullata, deve essere chiamato un metodo per consentire l'esecuzione di codice utente durante il processo.|  
|<xref:System.Runtime.InteropServices.ComVisibleAttribute>|Rende i tipi invisibili a COM quando il valore dell'attributo è **false**. Questo attributo può essere applicato a un tipo singolo o a un intero assembly per controllare la visibilità COM. Tutti i tipi gestiti e pubblici sono visibili per impostazione predefinita. Non è necessario usare questo attributo per renderli visibili.|  
|<xref:System.Runtime.InteropServices.DispIdAttribute>|Specifica l'identificatore di invio (DISPID) COM di un metodo o un campo. Questo attributo contiene il DISPID per il metodo, il campo o la proprietà che descrive.<br /><br /> Questo attributo può essere applicato dagli strumenti di interoperabilità COM.|
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute>|Indica l'interfaccia predefinita per una classe COM implementata in .NET.<br /><br /> Questo attributo può essere applicato dagli strumenti di interoperabilità COM.|
|<xref:System.Runtime.InteropServices.FieldOffsetAttribute>|Indica la posizione fisica di ogni campo all'interno di una classe quando è usato con l'attributo **StructLayoutAttribute** e **LayoutKind** è impostato su Explicit.|  
|<xref:System.Runtime.InteropServices.GuidAttribute>|Specifica l'identificatore univoco globale (GUID) di una classe, un'interfaccia o un'intera libreria dei tipi. Il formato della stringa passata all'attributo deve essere un argomento di costruttore accettabile per il tipo **System.Guid**.<br /><br /> Questo attributo può essere applicato dagli strumenti di interoperabilità COM.|  
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute>|Indica quale implementazione dell'interfaccia **IDispatch** viene usata da Common Language Runtime quando espone a COM interfacce duali e dispatch.|  
|<xref:System.Runtime.InteropServices.InAttribute>|Indica che è necessario effettuare il marshalling dei dati verso il chiamante. Può essere usato per i parametri.|  
|<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>|Controlla in che modo un'interfaccia gestita viene esposta ai client COM (duale, derivata da IUnknown o solo IDispatch).<br /><br /> Questo attributo può essere applicato dagli strumenti di interoperabilità COM.|  
|<xref:System.Runtime.InteropServices.LCIDConversionAttribute>|Indica che una firma di metodo non gestito accetta un parametro LCID.<br /><br /> Questo attributo può essere applicato dagli strumenti di interoperabilità COM.|  
|<xref:System.Runtime.InteropServices.MarshalAsAttribute>|Indica come deve essere effettuato il marshalling dei dati di campi o parametri tra codice gestito e codice non gestito. L'attributo è sempre facoltativo perché per ogni tipo di dati è previsto un comportamento di marshalling predefinito.<br /><br /> Questo attributo può essere applicato dagli strumenti di interoperabilità COM.|  
|<xref:System.Runtime.InteropServices.OptionalAttribute>|Indica che un parametro è facoltativo.<br /><br /> Questo attributo può essere applicato dagli strumenti di interoperabilità COM.|  
|<xref:System.Runtime.InteropServices.OutAttribute>|Indica che è necessario effettuare il marshalling dei dati di un campo o di un parametro da un oggetto chiamato al relativo chiamante.|  
|<xref:System.Runtime.InteropServices.PreserveSigAttribute>|Disattiva la trasformazione della firma retval o HRESULT che normalmente ha luogo durante le chiamate di interoperabilità. L'attributo influisce sul marshalling e sull'esportazione delle librerie dei tipi.<br /><br /> Questo attributo può essere applicato dagli strumenti di interoperabilità COM.|  
|<xref:System.Runtime.InteropServices.ProgIdAttribute>|Specifica il ProgID di una classe .NET Framework. Può essere usato per le classi.|  
|<xref:System.Runtime.InteropServices.StructLayoutAttribute>|Controlla il layout fisico dei campi di una classe.<br /><br /> Questo attributo può essere applicato dagli strumenti di interoperabilità COM.|  
  
## <a name="conversion-tool-attributes"></a>Attributi degli strumenti di conversione  
 La tabella seguente descrive gli attributi applicati dagli strumenti di interoperabilità COM durante il processo di conversione. Questi attributi non devono essere applicati in fase di progettazione.  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|<xref:System.Runtime.InteropServices.ComAliasNameAttribute>|Indica l'alias COM per un tipo di parametro o campo. Può essere usato per parametri, campi o valori restituiti.|  
|<xref:System.Runtime.InteropServices.ComConversionLossAttribute>|Indica che le informazioni relative a una classe o a un'interfaccia sono andate perse durante l'importazione da una libreria dei tipi a un assembly.|  
|<xref:System.Runtime.InteropServices.ComEventInterfaceAttribute>|Identifica l'interfaccia di origine e la classe che implementa i metodi dell'interfaccia eventi.|  
|<xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>|Indica che l'assembly è stato importato in origine da una libreria dei tipi COM. Questo attributo contiene la definizione della libreria dei tipi di origine.|  
|<xref:System.Runtime.InteropServices.TypeLibFuncAttribute>|Contiene i **FUNCFLAGS** importati in origine per questa funzione dalla libreria dei tipi COM.|  
|<xref:System.Runtime.InteropServices.TypeLibTypeAttribute>|Contiene i **TYPEFLAGS** importati in origine per questo tipo dalla libreria dei tipi COM.|  
|<xref:System.Runtime.InteropServices.TypeLibVarAttribute>|Contiene i **VARFLAGS** importati in origine per questa variabile dalla libreria dei tipi COM.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices>
- [Esposizione di componenti .NET Framework a COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)
- [Attributes (Attributi)](../../../docs/standard/attributes/index.md)
- [Qualificazione di tipi .NET per l'interoperabilità](../../../docs/standard/native-interop/qualify-net-types-for-interoperation.md)
- [Creazione di un pacchetto di un assembly .NET Framework per COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)
