
# Design bằng contract - Wikipedia


*Design bằng contract* (*DbC*), còn được biết là *lập trình contract*, *lập trình bằng contract* và *lập trình design-by-contract*,là 1 hướng tiếp cận để thiết kế phần mềm.Nó quy định rằng các nhà thiết kế phần mềm nên xác định chính thức, thông số giao diện chính xác và có thể kiểm chứng, nhằm mở rộng các định nghĩa thông thường của các loại dữ liệu trừu tượng  với  preconditions, postconditions va invariants. Những đặc tả này được gọi là "contract", phù hợp với một khái niệm ẩn dụ với các điều kiện và nghĩa vụ của  các contract công việc.

Cách tiếp cận DbC giả định tất cả các thành phần máy khách gọi một hoạt động trên một thành phần máy chủ sẽ đáp ứng các preconditions được xác định theo yêu cầu cho hoạt động đó. Trường hợp giả định này được coi là khá rủi ro (như trong máy khách đa kênh hoặc máy tính phân tán), phương pháp "thiết kế phòng thủ"  được thực hiện ngược lại, nghĩa là kiểm tra thành phần máy chủ (trước hoặc trong khi xử lý yêu cầu của khách hàng).rằng tất cả các điều kiện tiên quyết có liên quan đều đúng, và trả lời với một thông báo lỗi phù hợp nếu sai.

## Lịch sử
Thuật ngữ được đặt ra bởi Bertrand Meyer liên quan đến thiết kế của ông về ngôn ngữ lập trình Eiffel và được mô tả lần đầu trong các bài báo khác nhau bắt đầu từ năm 1986 [2] [3] và hai ấn bản liên tiếp (1988, 1997) Định hướng xây dựng phần mềm. Phần mềm Eiffel đã đăng ký nhãn hiệu cho Thiết kế theo Hợp đồng vào tháng 12 năm 2003 và được cấp vào tháng 12 năm 2004. [4] [5] Chủ sở hữu hiện tại của nhãn hiệu này là phần mềm Eiffel. [6] [7]
Thiết kế theo contract có nguồn gốc của nó trong công việc xác minh chính thức, đặc điểm kỹ thuật chính thức và logic Hoare. Những thành phần ban đầu bao gồm:
Một ẩn dụ rõ ràng để hướng dẫn quá trình thiết kế
Các ứng dụng để thừa kế, đặc biệt là một hình thức cho redefinition và ràng buộc động
Ứng dụng xử lý ngoại lệ
Kết nối với tài liệu phần mềm tự động
## Nội dung

Ý tưởng chính của DbC là một phép ẩn dụ về cách các yếu tố của một hệ thống phần mềm cộng tác với nhau trên cơ sở các nghĩa vụ và lợi ích chung. Ẩn dụ xuất phát từ cuộc sống công việc, nơi “khách hàng” và “nhà cung cấp” đồng ý với “hợp đồng” xác định, ví dụ:
* Nhà cung cấp phải cung cấp một sản phẩm nhất định (nghĩa vụ) và hi vọng khách hàng đã thanh toán phí (lợi ích) của mình.
* Khách hàng phải trả phí (nghĩa vụ) và được quyền nhận sản phẩm (lợi ích).
* Cả hai bên phải đáp ứng các nghĩa vụ nhất định, chẳng hạn như luật và quy định, áp dụng cho tất cả các hợp đồng.

Tương tự, nếu một đoạn chương trình từ một lớp trong lập trình hướng đối tượng cung cấp một chức năng nhất định, nó có thể:

* Mong đợi một điều kiện nhất định được đảm bảo khi nhập vào bởi bất kỳ mô-đun khách hàng nào gọi nó: điều kiện tiên quyết của đoạn ct đó - nghĩa vụ cho khách hàng và lợi ích cho nhà cung cấp (là chính nó), vì nó giải phóng nó khỏi phải xử lý các trường hợp bên ngoài precondition.
* Đảm bảo một thuộc tính nhất định về xuất cảnh :postconditions — một nghĩa vụ đối với nhà cung cấp, và rõ ràng là một lợi ích (lợi ích chính của việc gọi thường trình) cho khách hàng.
* Duy trì một tài sản nhất định, giả định về đầu vào và được bảo đảm khi thoát: lớp bất biến.

Hợp đồng này tương đương về mặt ngữ nghĩa với một luật Hoare triple,  hình thức hóa các nghĩa vụ. Điều này có thể được tóm tắt bằng "ba câu hỏi" mà nhà thiết kế phải nhiều lần trả lời trong hợp đồng:

* Hợp đồng kỳ vọng là gì?
* Bảo đảm hợp đồng là gì?
* Hợp đồng duy trì là gì?

Nhiều ngôn ngữ lập trình có cơ sở để đưa ra các xác nhận như thế này. Tuy nhiên, DbC coi các hợp đồng này là rất quan trọng đối với tính chính xác của phần mềm mà chúng phải là một phần của quá trình thiết kế. Trong thực tế, DbC chủ trương viết các xác nhận đầu tiên. Các hợp đồng có thể được viết bằng các chú thích code, được thi hành bởi một bộ kiểm thử, hoặc cả hai, ngay cả khi không có sự hỗ trợ ngôn ngữ đặc biệt cho các hợp đồng.

Khái niệm về hợp đồng kéo dài xuống mức phương thức / thủ tục; hợp đồng cho mỗi phương pháp thường sẽ chứa các thông tin sau: [_ citation needed_]

* Các giá trị hoặc loại đầu vào được chấp nhận và không được chấp nhận và ý nghĩa của chúng
* Trả lại giá trị hoặc loại và ý nghĩa của chúng
* Lỗi và các giá trị hoặc loại điều kiện ngoại lệ có thể xảy ra và ý nghĩa của chúng
* Tác dụng phụ
* Điều kiện tiên quyết
* Postconditions
* Bất biến
* (hiếm khi hơn) Đảm bảo hiệu suất, ví dụ: cho thời gian hoặc không gian được sử dụng

Các lớp con trong một hệ thống phân cấp thừa kế được phép làm suy yếu các điều kiện tiên quyết (nhưng không tăng cường chúng) và tăng cường các điều kiện và bất biến (nhưng không làm suy yếu chúng). Những quy tắc này gần đúng về phân loại hành vi.

Tất cả các mối quan hệ lớp nằm giữa giữa các lớp khách và các lớp nhà cung cấp. Một lớp khách có nghĩa vụ thực hiện các cuộc gọi đến các tính năng của nhà cung cấp, nơi trạng thái kết quả của nhà cung cấp không bị vi phạm bởi cuộc gọi của khách hàng. Sau đó, nhà cung cấp có nghĩa vụ cung cấp trạng thái trả lại và dữ liệu không vi phạm các yêu cầu của tiểu bang của khách hàng. Ví dụ, bộ đệm dữ liệu của nhà cung cấp có thể yêu cầu dữ liệu đó có trong bộ đệm khi một tính năng xóa được gọi. Sau đó, nhà cung cấp đảm bảo cho khách hàng rằng khi một tính năng xóa kết thúc công việc của nó, mục dữ liệu sẽ thực sự bị xóa khỏi bộ đệm. Các hợp đồng thiết kế khác là các khái niệm về “bất biến lớp”. Lớp bảo đảm bất biến (đối với lớp địa phương) rằng trạng thái của lớp sẽ được duy trì trong các dung sai được chỉ định ở cuối mỗi thực thi tính năng.

Khi sử dụng hợp đồng, nhà cung cấp không nên cố gắng xác minh rằng các điều kiện hợp đồng được thỏa mãn; ý tưởng chung là code sẽ "fail hard", với xác minh hợp đồng là mạng lưới an toàn.Thuộc tính "fail hard" của DbC đơn giản hoá việc gỡ rối hành vi hợp đồng, vì hành vi dự định của từng thói quen được xác định rõ ràng. Điều này phân biệt nó rõ ràng từ một thực hành liên quan được gọi là lập trình phòng thủ, nơi mà các nhà cung cấp chịu trách nhiệm cho việc tìm ra phải làm gì khi một preconditions bị phá vỡ.Trong một vài trường hợp, nhà cung cấp ném một ngoại lệ để thông báo cho khách hàng rằng preconditions đã bị phá vỡ, và trong cả hai trường hợp - DbC và lập trình phòng thủ — khách hàng phải tìm ra cách để đáp ứng điều đó. DbC giúp công việc của nhà cung cấp dễ dàng hơn.

Thiết kế theo hợp đồng cũng xác định tiêu chí cho tính chính xác cho một module phần mềm:

* Nếu lớp bất biến và preconditions là đúng trước khi một nhà cung cấp được gọi bởi một máy khách, thì sự bất biến và postcondition sẽ là đúng sau khi dịch vụ đã được hoàn thành.
* Khi thực hiện lời gọi đến nhà cung cấp, mô-đun phần mềm không được vi phạm các preconditions của nhà cung cấp.

Thiết kế theo hợp đồng cũng có thể tạo điều kiện tái sử dụng mã, vì hợp đồng cho từng đoạn mã được ghi chép đầy đủ. Các hợp đồng cho một mô-đun có thể được coi là một dạng tài liệu phần mềm cho hành vi của mô-đun đó.

## Ý nghĩa hiệu suất
Các điều kiện hợp đồng sẽ không bao giờ bị vi phạm trong khi thực hiện chương trình không có lỗi. Các hợp đồng do đó thường chỉ được kiểm tra trong chế độ gỡ lỗi trong quá trình phát triển phần mềm. Sau khi phát hành, kiểm tra hợp đồng bị vô hiệu hóa để tối đa hóa hiệu suất.

Trong nhiều ngôn ngữ lập trình, hợp đồng thực  hiện với các assert.Asserts được mặc định biên dịch trong chế độ phát hành trong C / C ++, và vô hiệu hóa tương tự trong C # [8] 27 và Java. Điều này có hiệu quả loại bỏ các chi phí thời gian chạy của hợp đồng phát hành.

## Mối quan hệ với kiểm thử phần mềm
Thiết kế theo hợp đồng không thay thế các chiến lược thử nghiệm thường xuyên, chẳng hạn như thử nghiệm đơn vị, thử nghiệm tích hợp và kiểm tra hệ thống. Thay vào đó, nó bổ sung cho thử nghiệm bên ngoài với các phép kiểm thử nội bộ có thể được kích hoạt cho cả các thử nghiệm riêng biệt và trong mã sản xuất trong giai đoạn thử nghiệm. Lợi thế của tự kiểm tra nội bộ là chúng có thể phát hiện lỗi trước khi chúng tự biểu hiện dưới dạng kết quả không hợp lệ được khách hàng quan sát. Điều này dẫn đến phát hiện lỗi sớm hơn và cụ thể hơn. 

Việc sử dụng các assert có thể được coi là một hình thức kiểm tra oracle, một cách để kiểm tra thiết kế bằng cách thực hiện hợp đồng.

##Language support
Ngôn ngữ có hỗ trợ gốc
Ngôn ngữ thực hiện hầu hết các tính năng của DbC bao gồm:

Ada 2012
Ciao
Clojure
Perl6
Cobra
D[9]
Eiffel
Fortress
Lisaac
Mercury
Nice
Oxygene (formerly Chrome and Delphi Prism[10])
Racket (including higher order contracts, and emphasizing that contract violations must blame the guilty party and must do so with an accurate explanation[11])
RPS-Obix
Sather
SPARK (via static analysis of Ada programs)
Spec#
Vala
VDM
Languages with third-party support	Edit
Various libraries, preprocessors and other tools have been developed for existing programming languages without native Design by Contract support:

Ada, via GNAT pragmas for preconditions and postconditions.
C and C++, via Boost.Contract, the DBC for C preprocessor, GNU Nana, eCv and eCv++ formal verification tools, or the Digital Mars C++ compiler, via CTESK extension of C. Loki Library provides a mechanism named ContractChecker that verifies a class follows design by contract.
C# (and other .NET languages), via Code Contracts[12] (a Microsoft Research project integrated into the .NET Framework 4.0)
Groovy via GContracts
Java:
Active:
OVal with AspectJ
Contracts for Java (Cofoja)
Java Modeling Language (JML)
Bean Validation (only pre- and postconditions)[13]
valid4j
Inactive/unknown:
Jtest (active but DbC seems not to be supported anymore)[14]
iContract2/JContracts
Contract4J
jContractor
C4J
Google CodePro Analytix
SpringContracts for the Spring Framework
Jass
Modern Jass (successor is Cofoja)[15][16]
JavaDbC using AspectJ
JavaTESK using extension of Java
chex4j using javassist
highly customizable java-on-contracts
JavaScript, via AspectJS (specifically, AJS_Validator), Cerny.js, ecmaDebug, jsContract, dbc-code-contracts or jscategory.
Common Lisp, via the macro facility or the CLOS metaobject protocol.
Nemerle, via macros.
Nim, via macros.
Perl, via the CPAN modules Class::Contract (by Damian Conway) or Carp::Datum (by Raphael Manfredi).
PHP, via PhpDeal, Praspel or Stuart Herbert's ContractLib.
Python, using packages like PyContracts, Decontractors, dpcontracts, zope.interface, PyDBC or Contracts for Python. A permanent change to Python to support Design by Contracts was proposed in PEP-316, but deferred.
Ruby, via Brian McCallister's DesignByContract, Ruby DBC ruby-contract or contracts.ruby.
Rust via the Hoare library
Tcl, via the XOTcl object-oriented extension.
See also	Edit
Component-based software engineering
Correctness (computer science)
Defensive programming
Fail-fast
Formal methods
Hoare logic
Modular programming
Program derivation
Program refinement
Test-driven development
Typestate analysis

 
