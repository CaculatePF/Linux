#include <opencv2/core/core.hpp>  
#include <opencv2/highgui/highgui.hpp> 
#include <opencv2/opencv.hpp>
#include <opencv2/imgproc/imgproc.hpp>
#include <iostream>
#include <vector>
   
using namespace cv;  
using namespace std;    


   
int main( )  
{  

Mat girl=imread("jia.jpg",IMREAD_GRAYSCALE); 
Mat arch;
resize(girl,arch,Size(),0.1,0.1);
namedWindow("原图");imshow("原图",arch);    
imwrite("x1.jpg",arch); 
//操作图像的像素点
//for(int i=0;i<arch.rows;i++)
//{
//	//for(int j=0;j<arch.cols;j++)
//	//{
//		arch.at<Vec3b>(i,i)[0]=0;
//		arch.at<Vec3b>(i,i)[1]=0;
//		arch.at<Vec3b>(i,i)[2]=255;
//	//}
//}
cout<<arch.channels()<<arch.depth();
namedWindow("新");imshow("新",arch);   

Mat kai=imread("kai.jpg",IMREAD_GRAYSCALE);
namedWindow("kai");imshow("kai",kai); 

Mat ma1(10,50, CV_8UC1,Scalar(111));
namedWindow("ma1");imshow("ma1",ma1); 

Mat sobelX,sobelY;
	cv::Sobel(arch,sobelX,CV_32F,1,0);
	cv::Sobel(arch,sobelY,CV_32F,0,1);
	cv::Mat sobel;
	//compute the L1 norm
	sobel= abs(sobelX)+abs(sobelY);
		double sobmin, sobmax,a,b;
	cv::minMaxLoc(sobel,&sobmin,&sobmax);
	//std::cout << "sobel value range: " << sobmin << "  " << sobmax << std::endl;

		//// Print window pixel values
		//for (int i=0; i<12; i++) {
		//	for (int j=0; j<12; j++)
		//		std::cout << std::setw(5) << static_cast<int>(sobel.at<short>(i+135,j+362)) << " ";
		//	std::cout << std::endl;
		//}
		//std::cout << std::endl;
		//std::cout << std::endl;
		//std::cout << std::endl;

	// Conversion to 8-bit image
	// sobelImage = alpha*sobel + 255
	cv::Mat sobelImage;
	a=-255./sobmax;
	b=-255/sobmax;
	sobel.convertTo(sobelImage,CV_8U,-255./sobmax,255);

    // Display the image
	cv::namedWindow("Sobel Image");
	cv::imshow("Sobel Image",sobelImage);


//// 把一个3通道图像转换成3个单通道图像   
//Mat channels[3]; 
//split(arch,channels); 
//namedWindow("sample");imshow("sample",channels[0]);  

////进行均值滤波操作  
//Mat out;
//GaussianBlur(arch,out,Size(3,3),0,0);
//namedWindow("均值滤波");imshow("均值滤波",out);
//  
//
////膨胀
//Mat element = getStructuringElement(MORPH_RECT, Size(3, 3)); 
//Mat dout;
//dilate(arch,dout,element);  
//namedWindow("膨胀操作");imshow("膨胀操作",dout);  
////腐蚀
//Mat eout;
//erode(arch,eout,element);
//namedWindow("腐蚀");imshow("腐蚀",eout);  
////形态学梯度
//Mat gout;
//morphologyEx(arch,gout,MORPH_GRADIENT,element);
//namedWindow("形态学梯度");imshow("形态学梯度",gout);  
//
//ctest t;
//ctest *p=&t;
//cout<<p<<endl<<&(p->c);





waitKey();
return 0;  
}  





/*Mat image= imread("pic.jpg");  
Mat logo= imread("12.png");  
   
//载入后先显示  
Mat im_a=image(Rect(80,350,100,100));
namedWindow("【2】");  
imshow("【2】",im_a);  

//定义一个Mat类型，用于存放，图像的ROI  
Mat imageROI;  
//方法一  
imageROI=image(Rect(800,350,logo.cols,logo.rows));  
std::cout<<logo.cols<<std::endl<<logo.rows;
//方法二  
//imageROI=image(Range(350,350+logo.rows),Range(800,800+logo.cols));  
   
//将logo加到原图上  
addWeighted(imageROI,0.5,logo,0.3,0.,imageROI);  
   
//显示结果  
namedWindow("【4】原画+logo图");  
imshow("【4】原画+logo图",image);  
   

   */
