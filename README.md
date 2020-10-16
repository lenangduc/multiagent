# multiagent
bài tập AI có đối thủ

=== Câu 1 ===
* mục tiêu: viết hàm đánh giá. 

* triển khai hàm đánh giá.
	- sử dụng manhattan tính khoảng cách đến đồ ăn. làm tham số để tính điểm của hàm đánh giá.
	- tính toán khoảng các đến đồ ăn và trả về giá trị min.

=== câu 2 ===

* Viết 1 hàm minimax với các tham số truyền vào như sau:
	- curr_depth: độ sâu của cây ở thời điểm hiện tại
	- agent_index: vị trị agent hiện tại
	- gamestate: trạng thái hiện tại của game.
	--> và trả về action và score.
* Triển khai hàm minimax:
	- xét agent_index. nếu agent đã hoàn thành nước di chuyển thì tăng curr_depth
	- trả về giá trị của hàm đánh giá khi đạt đến max depth.
	- khởi tạo best_score và best_action với giá trị default là none. 
	- nếu pacman đã hoàn thành lượt chơi:
		+ lấy giá trị của hàm minimax của điểm tiếp theo
	 	+ thì tăng giá trị cho agent_index để lượt tiếp theo là của ghost.
		+ update best_score và best_action. 
	- nếu ghost đã hoàn thành lượt chơi:
		+ lấy giá trị của hàm minimax của điểm tiếp theo
		+ tăng giá trị cho agent_index để lượt tiếp theo là của ghost
		+ update điểm số cao nhất và action. 
	- nếu không có state tiếp theo thì return về điểm đánh giá.
	- sau đó trả về best_action và best_score

=== câu 3 ===
* viết hàm alpha_beta với các tham số truyền vào và trả lại các tham số sau:
	- curr_depth: độ sâu của cây ở thời điểm hiện tại
	- agent_index: vị trị agent hiện tại
	- gamestate: trạng thái hiện tại của game.
	- alpha: là giá trị alpha của parent.
	- beta: là giá trị beta của parent. 
	- return: action và score. 
* triển khai hàm alpha_beta. 
	- xét agent_index. nếu agent đã hoàn thành nước di chuyển thì tăng curr_depth
	- trả về giá trị của hàm đánh giá khi đạt đến max depth.
	- khởi tạo best_score và best_action với giá trị default là none. 
	- nếu pacman đã hoàn thành lượt chơi:
		+ lấy giá trị của hàm alpha_beta của điểm tiếp theo
	 	+ thì tăng giá trị cho agent_index để lượt tiếp theo là của ghost.
		+ update điểm số cao nhất và action. 
		+ update giá trị là alpha với giá trị max
		+ tỉa cây nếu alpha lớn hơn beta.
	- nếu ghost đã hoàn thành lượt chơi:
		+ lấy giá trị của hàm alpha_beta của điểm tiếp theo
		+ tăng giá trị cho agent_index để lượt tiếp theo là của ghost
		+ update best_score và best_action. 
		+ update giá trị là beta với giá trị max
		+ tỉa cây nếu beta lớn hơn alpha
	- nếu không có state tiếp theo thì return về điểm đánh giá.
	- sau đó trả về best_action và best_score

=== câu 4 === 
* viết hàm Expectimax với các tham số truyền vào và trả lại như sau:
	- tương tự như câu 2. 
* triển khai hàm Expectimax: 
	- xét agent_index. nếu agent đã hoàn thành nước di chuyển thì tăng curr_depth
	- trả về giá trị của hàm đánh giá khi đạt đến max depth.
	- khởi tạo best_score và best_action với giá trị default là none. 
	- nếu pacman đã hoàn thành lượt chơi:
		+ lấy giá trị của hàm Expectimax: của điểm tiếp theo
	 	+ thì tăng giá trị cho agent_index để lượt tiếp theo là của ghost.
		+ update điểm số cao nhất và action. 
	- nếu ghost đã hoàn thành lượt chơi:
		+ lấy giá trị của hàm Expectimax: của điểm tiếp theo
		+ tăng giá trị cho agent_index để lượt tiếp theo là của ghost
		+ update best_score = score * (1/ độ dài action của ghost) và best_action. 
	- nếu không có state tiếp theo thì return về điểm đánh giá.
	- sau đó trả về best_action và best_score
	



