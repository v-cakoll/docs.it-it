---
title: 'Procedura: eseguire il mapping di HRESULT ed eccezioni'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- interoperation with unmanaged code, HRESULTs
- exceptions, HRESULTs
- interoperation with unmanaged code, exceptions
- HRESULTs
- COM interop, HRESULTs
- COM interop, exceptions
ms.assetid: 610b364b-2761-429d-9c4a-afbc3e66f1b9
ms.openlocfilehash: e186228d1dc9a42ddfe92428f7dfad29a5789095
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181401"
---
# <a name="how-to-map-hresults-and-exceptions"></a>Procedura: eseguire il mapping di HRESULT ed eccezioni
I metodi COM segnalano gli errori restituendo HRESULT, mentre i metodi .NET li segnalano generando eccezioni. Il runtime gestisce la transizione tra questi due approcci. Ogni classe di eccezione in .NET Framework viene mappata a un HRESULT.  
  
 Le classi di eccezioni definite dall'utente possono specificare un HRESULT appropriato. Queste classi di eccezione possono modificare dinamicamente il valore HRESULT da restituire quando viene generata l'eccezione impostando il campo **HResult** per l'oggetto eccezione. Informazioni aggiuntive sull'eccezione vengono fornite al client tramite l'interfaccia **IErrorInfo**, implementata per l'oggetto .NET nel processo non gestito.  
  
 Se si crea una classe che estende **System. Exception**, è necessario impostare il campo HRESULT durante la costruzione. In caso contrario, la classe di base assegna il valore HRESULT. È possibile mappare nuove classi di eccezione a un HRESULT esistente specificando il valore nel costruttore dell'eccezione.  
  
 Si noti che il runtime a volte ignorerà un `HRESULT` nei casi in cui nel thread è presente `IErrorInfo`.  Questo comportamento può verificarsi nei casi in cui `HRESULT` e `IErrorInfo` non rappresentano lo stesso errore.  
  
### <a name="to-create-a-new-exception-class-and-map-it-to-an-hresult"></a>Per creare una nuova classe di eccezione ed eseguirne il mapping a un HRESULT  
  
1. Usare il codice seguente per creare una nuova classe di eccezione denominata `NoAccessException` ed eseguirne il mapping al valore HRESULT `E_ACCESSDENIED`.  
  
    ```cpp  
    Class NoAccessException : public ApplicationException  
    {  
        NoAccessException () {  
        HResult = E_ACCESSDENIED;
    }  
    }  
    CMyClass::MethodThatThrows  
    {  
    throw new NoAccessException();  
    }  
    ```  
  
 Possono esistere programmi, scritti con qualsiasi linguaggio, che usano codice gestito e non gestito contemporaneamente. Ad esempio, il gestore di marshalling personalizzato nell'esempio di codice seguente usa il metodo **Marshal.ThrowExceptionForHR (int HResult)** per generare un'eccezione con un valore HRESULT specifico. Il metodo cerca il valore HRESULT e genera il tipo di eccezione appropriato. Ad esempio, il valore HRESULT nel frammento di codice seguente genera **ArgumentException**.  
  
```cpp  
CMyClass::MethodThatThrows  
{  
    Marshal.ThrowExceptionForHR(COR_E_ARGUMENT);  
}  
```  
  
 La tabella seguente illustra i mapping completi tra ogni oggetto HRESULT e la classe di eccezioni corrispondente in .NET Framework.  
  
|HRESULT|Eccezione .NET|  
|-------------|--------------------|  
|**MSEE_E_APPDOMAINUNLOADED**|**AppDomainUnloadedException**|  
|**COR_E_APPLICATION**|**ApplicationException**|  
|**COR_E_ARGUMENT o E_INVALIDARG**|**ArgumentException**|  
|**COR_E_ARGUMENTOUTOFRANGE**|**ArgumentOutOfRangeException**|  
|**COR_E_ARITHMETIC o ERROR_ARITHMETIC_OVERFLOW**|**ArithmeticException**|  
|**COR_E_ARRAYTYPEMISMATCH**|**ArrayTypeMismatchException**|  
|**COR_E_BADIMAGEFORMAT o ERROR_BAD_FORMAT**|**BadImageFormatException**|  
|**COR_E_COMEMULATE_ERROR**|**COMEmulateException**|  
|**COR_E_CONTEXTMARSHAL**|**ContextMarshalException**|  
|**COR_E_CORE**|**Coreexception**|  
|**NTE_FAIL**|**CryptographicException**|  
|**COR_E_DIRECTORYNOTFOUND o ERROR_PATH_NOT_FOUND**|**DirectoryNotFoundException**|  
|**COR_E_DIVIDEBYZERO**|**DivideByZeroException**|  
|**COR_E_DUPLICATEWAITOBJECT**|**DuplicateWaitObjectException**|  
|**COR_E_ENDOFSTREAM**|**EndOfStreamException**|  
|**COR_E_TYPELOAD**|**EntryPointNotFoundException**|  
|**COR_E_EXCEPTION**|**Eccezione**|  
|**COR_E_EXECUTIONENGINE**|**ExecutionEngineException**|  
|**COR_E_FIELDACCESS**|**FieldAccessException**|  
|**COR_E_FILENOTFOUND o ERROR_FILE_NOT_FOUND**|**FileNotFoundException**|  
|**COR_E_FORMAT**|**FormatException**|  
|**COR_E_INDEXOUTOFRANGE**|**IndexOutOfRangeException**|  
|**COR_E_INVALIDCAST o E_NOINTERFACE**|**InvalidCastException**|  
|**COR_E_INVALIDCOMOBJECT**|**InvalidComObjectException**|  
|**COR_E_INVALIDFILTERCRITERIA**|**InvalidFilterCriteriaException**|  
|**COR_E_INVALIDOLEVARIANTTYPE**|**InvalidOleVariantTypeException**|  
|**COR_E_INVALIDOPERATION**|**InvalidOperationException**|  
|**COR_E_IO**|**IOException**|  
|**COR_E_MEMBERACCESS**|**AccessException**|  
|**COR_E_METHODACCESS**|**MethodAccessException**|  
|**COR_E_MISSINGFIELD**|**MissingFieldException**|  
|**COR_E_MISSINGMANIFESTRESOURCE**|**MissingManifestResourceException**|  
|**COR_E_MISSINGMEMBER**|**MissingMemberException**|  
|**COR_E_MISSINGMETHOD**|**MissingMethodException**|  
|**COR_E_MULTICASTNOTSUPPORTED**|**MulticastNotSupportedException**|  
|**COR_E_NOTFINITENUMBER**|**NotFiniteNumberException**|  
|**E_NOTIMPL**|**NotImplementedException**|  
|**COR_E_NOTSUPPORTED**|**NotSupportedException**|  
|**COR_E_NULLREFERENCE o E_POINTER**|**NullReferenceException**|  
|**COR_E_OUTOFMEMORY o**<br /><br /> **E_OUTOFMEMORY**|**OutOfMemoryException**|  
|**COR_E_OVERFLOW**|**OverflowException**|  
|**COR_E_PATHTOOLONG o ERROR_FILENAME_EXCED_RANGE**|**PathTooLongException**|  
|**COR_E_RANK**|**RankException**|  
|**COR_E_REFLECTIONTYPELOAD**|**ReflectionTypeLoadException**|  
|**COR_E_REMOTING**|**RemotingException**|  
|**COR_E_SAFEARRAYTYPEMISMATCH**|**SafeArrayTypeMismatchException**|  
|**COR_E_SECURITY**|**SecurityException**|  
|**COR_E_SERIALIZATION**|**SerializationException**|  
|**COR_E_STACKOVERFLOW o ERROR_STACK_OVERFLOW**|**StackOverflowException**|  
|**COR_E_SYNCHRONIZATIONLOCK**|**SynchronizationLockException**|  
|**COR_E_SYSTEM**|**SystemException**|  
|**COR_E_TARGET**|**TargetException**|  
|**COR_E_TARGETINVOCATION**|**TargetInvocationException**|  
|**COR_E_TARGETPARAMCOUNT**|**TargetParameterCountException**|  
|**COR_E_THREADABORTED**|**ThreadAbortException**|  
|**COR_E_THREADINTERRUPTED**|**ThreadInterruptedException**|  
|**COR_E_THREADSTATE**|**ThreadStateException**|  
|**COR_E_THREADSTOP**|**ThreadStopException**|  
|**COR_E_TYPELOAD**|**TypeLoadException**|  
|**COR_E_TYPEINITIALIZATION**|**TypeInitializationException**|  
|**COR_E_VERIFICATION**|**VerificationException**|  
|**COR_E_WEAKREFERENCE**|**WeakReferenceException**|  
|**COR_E_VTABLECALLSNOTSUPPORTED**|**VTableCallsNotSupportedException**|  
|**Tutti gli altri HRESULT**|**COMException**|  
  
 Per recuperare informazioni dettagliate sull'errore, il client gestito deve esaminare i campi dell'oggetto eccezione generato. Affinché l'oggetto eccezione possa fornire informazioni utili su un errore, è necessario che l'oggetto COM implementi l'interfaccia **IErrorInfo**. Il runtime usa le informazioni fornite da **IErrorInfo** per inizializzare l'oggetto eccezione.  
  
 Se l'oggetto COM non supporta **IErrorInfo**, il runtime Inizializza un oggetto eccezione con i valori predefiniti. La tabella seguente elenca ogni campo associato a un oggetto eccezione e identifica l'origine delle informazioni predefinite quando l'oggetto COM supporta **IErrorInfo**.  
  
 Si noti che il runtime a volte ignorerà un `HRESULT` nei casi in cui nel thread è presente `IErrorInfo`.  Questo comportamento può verificarsi nei casi in cui `HRESULT` e `IErrorInfo` non rappresentano lo stesso errore.  
  
|Campo eccezione|Fonte di informazioni da COM|  
|---------------------|------------------------------------|  
|**ErrorCode**|HRESULT restituito dalla chiamata.|  
|**HelpLink**|Se **IErrorInfo-> HelpContext** è diverso da zero, la stringa viene formata concatenando **IErrorInfo ->GetHelpFile** e "#" e **IErrorInfo ->GetHelpContext**. In caso contrario, la stringa viene restituita da **IErrorInfo ->GetHelpFile**.|  
|**InnerException**|Sempre un riferimento null (**Nothing** in Visual Basic).|  
|**Messaggio**|Stringa restituita da **IErrorInfo->GetDescription**.|  
|**origine**|Stringa restituita da **IErrorInfo->GetSource**.|  
|**StackTrace**|Analisi dello stack.|  
|**TargetSite**|Nome del metodo che ha restituito il valore HRESULT in errore.|  
  
 I campi di eccezione, ad esempio **Message**, **Source** e **StackTrace** non sono disponibili per **StackOverflowException**.  
  
## <a name="see-also"></a>Vedere anche

- [Interoperabilità COM avanzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))
- [Eccezioni](../../standard/exceptions/index.md)
