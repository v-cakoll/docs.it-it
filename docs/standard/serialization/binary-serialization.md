---
title: Serializzazione binaria
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 34ba6cb658a52b647c6fbf9a4161d046f31cd73e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705821"
---
# <a name="binary-serialization"></a>Serializzazione binaria

La serializzazione può essere definita come il processo di archiviazione dello stato di un oggetto su un supporto di archiviazione. Durante tale processo, i campi pubblici e privati dell'oggetto e il nome della classe, incluso l'assembly contenente la classe, vengono convertiti in un flusso di byte che viene scritto in un flusso di dati. Quando l'oggetto viene successivamente deserializzato, viene creato un clone esatto dell'oggetto originale.

Quando si implementa un meccanismo di serializzazione in un ambiente orientato agli oggetti, è necessario fare una serie di compromessi tra semplicità di utilizzo e flessibilità. Il processo può essere automatizzato in un ambito di grandi dimensioni, purché si disponga di controllo sufficiente sul processo. Ad esempio, possono verificarsi situazioni in cui non è sufficiente la semplice serializzazione binaria o potrebbe esserci una ragione specifica per decidere quali campi in una classe devono essere serializzati. Nelle sezioni seguenti viene esaminato l'avanzato meccanismo di serializzazione fornito con .NET e vengono evidenziate alcune importanti funzionalità che consentono di personalizzare il processo in base alle esigenze.

> [!NOTE]
> Lo stato di un oggetto codificato UTF-7 o UTF-8 non viene mantenuto se le relative operazioni di serializzazione e deserializzazione vengono eseguite con versioni di .NET Framework diverse.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

Poiché la natura della serializzazione binaria consente la modifica di membri privati all'interno di un oggetto e quindi la modifica dello stato dell'oggetto, sono consigliati altri framework di serializzazione, come JSON.NET, che intervengono sulla superficie dell'API pubblica.

## <a name="binary-serialization-in-net-core"></a>Serializzazione binaria in .NET Core

.NET Core supporta la serializzazione binaria con un subset di tipi. È possibile consultare l'elenco dei tipi supportati nella sezione [Tipi serializzabili](#serializable-types). È garantita la serializzazione dei tipi definiti tra .NET Framework 4.5.1 e versioni successive e tra .NET Core 2.0 e versioni successive. Altre implementazioni di .NET, ad esempio Mono, non sono ufficialmente supportate ma dovrebbero comunque funzionare.

### <a name="serializable-types"></a>Tipi serializzabili

- <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.AccessViolationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.AggregateException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ApplicationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ArgumentException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ArgumentNullException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ArithmeticException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Array?displayProperty=nameWithType>
- <xref:System.ArraySegment%601?displayProperty=nameWithType>
- <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Attribute?displayProperty=nameWithType>
- <xref:System.BadImageFormatException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Boolean?displayProperty=nameWithType>
- <xref:System.Byte?displayProperty=nameWithType>
- <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Char?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList?displayProperty=nameWithType>
- <xref:System.Collections.BitArray?displayProperty=nameWithType>
- <xref:System.Collections.Comparer?displayProperty=nameWithType>
- <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType>
- <xref:System.Collections.Hashtable?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.Queue?displayProperty=nameWithType>
- <xref:System.Collections.SortedList?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Stack?displayProperty=nameWithType>
- `System.Collections.Generic.NonRandomizedStringEqualityComparer` (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive, la serializzazione da .NET Framework a .NET Core non è supportata)
- <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ContextMarshalException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DBNull?displayProperty=nameWithType> (disponibile in .NET Core 2.0.2 e versioni successive)
- <xref:System.Data.Common.DbException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.ConstraintException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.DataException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.DataSet?displayProperty=nameWithType>
- <xref:System.Data.DataTable?displayProperty=nameWithType> (a meno che non si imposti RemotingFormat su SerializationFormat. Binary, in questo caso può essere scambiato solo con .NET Core 2,1 e versioni successive).
- <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.EvaluateException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.PropertyCollection?displayProperty=nameWithType>
- <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive, la serializzazione da .NET Framework a .NET Core non è supportata)
- <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.StrongTypingException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DataMisalignedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DateTime?displayProperty=nameWithType>
- <xref:System.DateTimeOffset?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- `System.Diagnostics.Contracts.ContractException` (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DivideByZeroException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.DllNotFoundException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Drawing.Color?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- <xref:System.Drawing.PointF?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- <xref:System.Drawing.RectangleF?displayProperty=nameWithType>
- <xref:System.Drawing.Size?displayProperty=nameWithType>
- <xref:System.Drawing.SizeF?displayProperty=nameWithType>
- <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Enum?displayProperty=nameWithType>
- <xref:System.EventArgs?displayProperty=nameWithType> (disponibile in .NET Core 2.0.6 e versioni successive)
- <xref:System.Exception?displayProperty=nameWithType>
- <xref:System.ExecutionEngineException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.FieldAccessException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.FormatException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Globalization.CompareInfo?displayProperty=nameWithType>
- <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Globalization.SortVersion?displayProperty=nameWithType>
- <xref:System.Guid?displayProperty=nameWithType>
- `System.IO.Compression.ZLibException` (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IO.FileFormatException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IO.FileLoadException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IO.IOException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IO.InvalidDataException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IO.PathTooLongException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.InsufficientMemoryException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Int16?displayProperty=nameWithType>
- <xref:System.Int32?displayProperty=nameWithType>
- <xref:System.Int64?displayProperty=nameWithType>
- <xref:System.IntPtr?displayProperty=nameWithType>
- <xref:System.InvalidCastException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.InvalidOperationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.InvalidProgramException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.MemberAccessException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.MethodAccessException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.MissingFieldException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.MissingMemberException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.MissingMethodException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Net.Cookie?displayProperty=nameWithType>
- <xref:System.Net.CookieCollection?displayProperty=nameWithType>
- <xref:System.Net.CookieContainer?displayProperty=nameWithType>
- <xref:System.Net.CookieException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Net.HttpListenerException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Net.WebException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.NotFiniteNumberException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.NotImplementedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.NotSupportedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.NullReferenceException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Numerics.BigInteger?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.ObjectDisposedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.OperationCanceledException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.OutOfMemoryException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.OverflowException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.RankException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive, la serializzazione da .NET Framework a .NET Core non è supportata)
- <xref:System.Reflection.TargetException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.SByte?displayProperty=nameWithType>
- <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Security.HostProtectionException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Security.SecurityException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive, dati di serializzazione limitati)
- <xref:System.Security.VerificationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.StackOverflowException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.StringComparer?displayProperty=nameWithType>
- <xref:System.SystemException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Text.StringBuilder?displayProperty=nameWithType>
- <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.TimeSpan?displayProperty=nameWithType>
- <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType>
- <xref:System.TimeZoneInfo?displayProperty=nameWithType>
- <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.TimeoutException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Transactions.TransactionException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Tuple?displayProperty=nameWithType>
- <xref:System.TypeAccessException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.TypeInitializationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.TypeLoadException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.TypeUnloadedException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.UInt16?displayProperty=nameWithType>
- <xref:System.UInt32?displayProperty=nameWithType>
- <xref:System.UInt64?displayProperty=nameWithType>
- <xref:System.UIntPtr?displayProperty=nameWithType>
- <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Uri?displayProperty=nameWithType>
- <xref:System.UriFormatException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.ValueTuple?displayProperty=nameWithType> (non serializzabile in .NET Framework 4,7 e versioni precedenti)
- <xref:System.ValueType?displayProperty=nameWithType>
- <xref:System.Version?displayProperty=nameWithType>
- <xref:System.WeakReference%601?displayProperty=nameWithType>
- <xref:System.WeakReference?displayProperty=nameWithType>
- <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Xml.XmlException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)
- <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> (disponibile in .NET Core 2.0.4 e versioni successive)

## <a name="in-this-section"></a>In questa sezione

- [Concetti di serializzazione](../../../docs/standard/serialization/serialization-concepts.md)\
Vengono illustrati due scenari in cui la serializzazione risulta utile: quando si conservano i dati da archiviare e quando si trasferiscono oggetti tra più domini dell'applicazione.

- [Serializzazione di base](../../../docs/standard/serialization/basic-serialization.md)\
Descrive come utilizzare i formattatori binari e SOAP per serializzare gli oggetti.

- \ di [serializzazione selettiva](../../../docs/standard/serialization/selective-serialization.md)
Descrive come impedire la serializzazione di alcuni membri di una classe.

- \ di [serializzazione personalizzata](../../../docs/standard/serialization/custom-serialization.md)
Descrive come personalizzare la serializzazione per una classe usando l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.

- [Passaggi del processo di serializzazione](../../../docs/standard/serialization/steps-in-the-serialization-process.md)\
Descrive il corso di azioni intraprese dalla serializzazione quando viene chiamato il metodo <xref:System.Runtime.Serialization.Formatter.Serialize%2A> su un formattatore.

- [Serializzazione a tolleranza di versione](../../../docs/standard/serialization/version-tolerant-serialization.md)\
Spiega come creare tipi serializzabili modificabili nel tempo evitando che le applicazioni generino eccezioni.

- [Linee guida sulla serializzazione](../../../docs/standard/serialization/serialization-guidelines.md)\
Fornisce alcune linee guida generali che consentono di decidere quando serializzare un oggetto.

## <a name="reference"></a>Riferimenti

- <xref:System.Runtime.Serialization>\
Contiene classi utilizzabili per la serializzazione e la deserializzazione di oggetti.

## <a name="related-sections"></a>Sezioni correlate

- [Serializzazione SOAP e XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)\
Descrive il meccanismo della serializzazione XML incluso nel Common Language Runtime.

- [Sicurezza e serializzazione](../../../docs/framework/misc/security-and-serialization.md)\
Descrive le linee guida per la creazione di codice protetto da seguire in caso di scrittura di codice che esegue la serializzazione.

- \ [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))
Vengono descritti i diversi metodi di comunicazione disponibili in .NET Framework per le comunicazioni remote.

- [I servizi Web XML creati utilizzando ASP.NET e i client del servizio Web xml](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))\
Fornisce gli argomenti che descrivono e spiegano come programmare i servizi Web XML creati tramite ASP.NET.
