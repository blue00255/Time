package com.example.time;

import androidx.appcompat.app.AppCompatActivity;

import android.graphics.Color;
import android.os.Bundle;
import android.view.Gravity;
import android.view.View;
import android.widget.EditText;
import android.widget.LinearLayout;
import android.widget.TextView;
import android.widget.Toast;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;
import java.util.Calendar;
import java.util.Date;

public class MainActivity extends AppCompatActivity
{
    EditText start_time;
    EditText end_time;
    EditText begin_time;
    EditText all_days;

    String time= LocalDate.now().format(DateTimeFormatter.ofPattern("yyyy-MM-dd"));
    String time1= LocalDate.now().format(DateTimeFormatter.ofPattern("yyyy.MM.dd"));
    //这是为了设置输入框的提示内容，这里设置的是当前时间




    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        start_time=(EditText)findViewById(R.id.time_start) ;  //获得时间间隔开始时间控件
        start_time.setHint(time+"/"+time1);//设置显示框的提示时间，默认时间是当前的时间
        end_time=(EditText)findViewById(R.id.time_end);   //获得时间间隔结束时间控件
        end_time.setHint(time+"/"+time1);//同上
        begin_time=(EditText)findViewById(R.id.time_begin);//获得时间推算的开始时间控件
        begin_time.setHint(time+"/"+time1);//同上
        all_days=(EditText)findViewById(R.id.days);   //获得推算时间所用到的天数

    }


    //这个函数是计算时间间隔的函数
    public void Lcc_happy(View view) throws ParseException
    {
        String start=start_time.getText().toString().trim();  //获得输入框中的时间
        StringBuffer start_buffer=new StringBuffer(start);   //将获得的时间进行类型转换，从String到StringBuffer
        String end=end_time.getText().toString().trim();     //获得输入框中的时间
        StringBuffer end_buffer=new StringBuffer(end);      //将获得的时间进行类型转换，从String到StringBuffer
        int start_length=start.length();  //获得输入框中内容的长度，以此来判断是否输入合法
        int end_length=end.length();

        //准备在这里添加一个判断长度是否为零的逻辑，也就是如果不输入任何内容，我们就把当前时间当做默认的计算时间。

        if(start_length==0||end_length==0)
        {
            if(start_length==0)
            {
                start= LocalDate.now().format(DateTimeFormatter.ofPattern("yyyy-MM-dd")).toString().trim();
                start_buffer=new StringBuffer(start);
                start_length=start.length();  //获得输入框中内容的长度，以此来判断是否输入合法

            }
            if(end_length==0)
            {
                end=LocalDate.now().format(DateTimeFormatter.ofPattern("yyyy-MM-dd")).toString().trim();
                end_buffer=new StringBuffer(end);
                end_length=end.length();
            }
        }

        if(start_length<8||start_length>10||end_length<8||end_length>10)   //判断输入是否合法的逻辑语句
        {
            if(start_length<8||start_length>10)
            {
                Toast.makeText(this,"输入错误,重新输入",Toast.LENGTH_SHORT).show();
                start_time.setText("");
                return;
            }
            if(end_length<8||end_length>10)
            {
                Toast.makeText(this,"输入错误,重新输入",Toast.LENGTH_SHORT).show();
                end_time.setText("");
                return;
            }
        }
        char c=start.charAt(4);
        char c1=end.charAt(4);
        if(c=='-')
        {
            if(start_length==10)
            {
                if(start.charAt(7)!='-')
                {
                    Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                    start_time.setText("");
                    return;
                }
            }
            SimpleDateFormat formatter1 = new SimpleDateFormat("yyyy-MM-dd");
            try {
                formatter1.parse(start);
            } catch (ParseException pe) {
                Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                start_time.setText("");
                return;
            }
        }
        else if(c=='.')
        {
            if(start_length==10)
            {
                if(start.charAt(7)!='.')
                {
                    Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                    start_time.setText("");
                    return;
                }
            }
            SimpleDateFormat formatter2 = new SimpleDateFormat("yyyy.MM.dd");
            try {
                formatter2.parse(start);
            } catch (ParseException pe) {
                Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                start_time.setText("");
                return;
            }
        }
        else
        {
            Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
            start_time.setText("");
            return;

        }

        if(c1=='-')
        {
            if(end_length==10)
            {
                if(end.charAt(7)!='-')
                {
                    Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                    end_time.setText("");
                    return;
                }
            }
            SimpleDateFormat formatter3 = new SimpleDateFormat("yyyy-MM-dd");
            try {
                formatter3.parse(end);
            } catch (ParseException pe) {
                Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                end_time.setText("");
                return;
            }
        }
        else if(c1=='.')
        {
            if(end_length==10)
            {
                if(end.charAt(7)!='.')
                {
                    Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                    end_time.setText("");
                    return;
                }
            }
            SimpleDateFormat formatter4 = new SimpleDateFormat("yyyy.MM.dd");
            try {
                formatter4.parse(end);
            } catch (ParseException pe) {
                Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                end_time.setText("");
                return;
            }
        }
        else
        {
            Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
            start_time.setText("");
            return;
        }





        //////////
        if(start_length==8)   //这是为了统一格式为2020.01.01或者2020-01-01
        {
            start_buffer.insert(5,0);
            start_buffer.insert(8,0);
        }
        else if(start_length==9)
        {
            if(start.charAt(7)=='-')
            {
                start_buffer.insert(8,0);
            }
            else {
                start_buffer.insert(5,0);
            }
        }
        if(end_length==8)
        {
            end_buffer.insert(5,0);
            end_buffer.insert(8,0);
        }
        else if(end_length==9)
        {
            if(end.charAt(7)=='-')
            {
                end_buffer.insert(8,0);
            }
            else {
                end_buffer.insert(5,0);
            }
        }
        String start1=new String(start_buffer);
        String end1=new String(end_buffer);
        int start_year=Integer.valueOf(start1.substring(0,4)).intValue();
        int start_month=Integer.valueOf(start1.substring(5, 7)).intValue();
        int start_day=Integer.valueOf(start1.substring(8, 10)).intValue();
        int end_year=Integer.valueOf(end1.substring(0,4)).intValue();
        int end_month=Integer.valueOf(end1.substring(5, 7)).intValue();
        int end_day=Integer.valueOf(end1.substring(8, 10)).intValue();
        if(start_year%4==0&&start_year%100!=0||start_year%400==0)  //如果是闰月
        {
            if(start_month>12)
            {
                Toast.makeText(this, "月份输入错误,重新输入", Toast.LENGTH_SHORT).show();
                start_time.setText("");
                return;
            }
            else
            {
                if(start_month==1||start_month==3||start_month==5||start_month==7||start_month==8||start_month==10||start_month==12)
                {
                    if(start_day>31)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        start_time.setText("");
                        return;
                    }
                }
                if(start_month==4||start_month==6||start_month==9||start_month==11)
                {
                    if(start_day>30)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        start_time.setText("");
                        return;
                    }
                }
                if(start_month==2)
                {
                    if(start_day>29)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        start_time.setText("");
                        return;
                    }
                }
            }
        }
        else   //如果不是闰月
        {
            if(start_month>12)
            {
                Toast.makeText(this, "月份输入错误,重新输入", Toast.LENGTH_SHORT).show();
                start_time.setText("");
                return;
            }
            else
            {
                if(start_month==1||start_month==3||start_month==5||start_month==7||start_month==8||start_month==10||start_month==12)
                {
                    if(start_day>31)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        start_time.setText("");
                        return;
                    }
                }
                if(start_month==4||start_month==6||start_month==9||start_month==11)
                {
                    if(start_day>30)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        start_time.setText("");
                        return;
                    }
                }
                if(start_month==2)
                {
                    if(start_day>28)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        start_time.setText("");
                        return;
                    }
                }
            }
        }
        if(end_year%4==0&&end_year%100!=0||end_year%400==0)  //如果是闰月
        {
            if(end_month>12)
            {
                Toast.makeText(this, "月份输入错误,重新输入", Toast.LENGTH_SHORT).show();
                end_time.setText("");
                return;
            }
            else
            {
                if(end_month==1||end_month==3||end_month==5||end_month==7||end_month==8||end_month==10||end_month==12)
                {
                    if(end_day>31)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        end_time.setText("");
                        return;
                    }
                }
                if(end_month==4||end_month==6||end_month==9||end_month==11)
                {
                    if(end_day>30)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        end_time.setText("");
                        return;
                    }
                }
                if(end_month==2)
                {
                    if(end_day>29)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        end_time.setText("");
                        return;
                    }
                }
            }
        }
        else   //如果不是闰月
        {
            if(end_month>12)
            {
                Toast.makeText(this, "月份输入错误,重新输入", Toast.LENGTH_SHORT).show();
                end_time.setText("");
                return;
            }
            else
            {
                if(end_month==1||end_month==3||end_month==5||end_month==7||end_month==8||end_month==10||end_month==12)
                {
                    if(end_day>31)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        end_time.setText("");
                        return;
                    }
                }
                if(end_month==4||end_month==6||end_month==9||end_month==11)
                {
                    if(end_day>30)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        end_time.setText("");
                        return;
                    }
                }
                if(end_month==2)
                {
                    if(end_day>28)
                    {
                        Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                        end_time.setText("");
                        return;
                    }
                }
            }

        }




        ////////

        if(c=='-'&&c1=='-')
        {
            SimpleDateFormat df=new SimpleDateFormat("yyyy-MM-dd");
            Date date1=df.parse(start1);
            Date date2=df.parse(end1);
            double between=(date1.getTime()-date2.getTime())/(1000*60*60*24);
            if(between<0.0)
            {
                between=-between;
            }
            String result=start1+"与"+end1+"相差"+between+"天";
            Toast.makeText(MainActivity.this,result,Toast.LENGTH_SHORT).show(); //将选择的日期显示出来
        }
        if(c=='.'&&c1=='.')
        {
            SimpleDateFormat df=new SimpleDateFormat("yyyy.MM.dd");
            Date date1=df.parse(start1);
            Date date2=df.parse(end1);
            double between=(date1.getTime()-date2.getTime())/(1000*60*60*24);
            if(between<0.0)
            {
                between=-between;
            }
            String result=start1+"与"+end1+"相差"+between+"天";
            Toast.makeText(MainActivity.this,result,Toast.LENGTH_SHORT).show(); //将选择的日期显示出来
        }
        if(c=='-'&&c1=='.')
        {
            SimpleDateFormat df=new SimpleDateFormat("yyyy-MM-dd");
            SimpleDateFormat df1=new SimpleDateFormat("yyyy.MM.dd");
            Date date1=df.parse(start1);
            Date date2=df1.parse(end1);
            double between=(date1.getTime()-date2.getTime())/(1000*60*60*24);
            if(between<0.0)
            {
                between=-between;
            }
            String result=start1+"与"+end1+"相差"+between+"天";
            Toast.makeText(MainActivity.this,result,Toast.LENGTH_SHORT).show(); //将选择的日期显示出来
        }

        if(c=='.'&&c1=='-')
        {
            SimpleDateFormat df=new SimpleDateFormat("yyyy.MM.dd");
            SimpleDateFormat df1=new SimpleDateFormat("yyyy-MM-dd");
            Date date1=df.parse(start1);
            Date date2=df1.parse(end1);
            double between=(date1.getTime()-date2.getTime())/(1000*60*60*24);
            if(between<0.0)
            {
                between=-between;
            }
            String result=start1+"与"+end1+"相差"+between+"天";
            Toast.makeText(MainActivity.this,result,Toast.LENGTH_SHORT).show(); //将选择的日期显示出来
        }


    }
   //这个函数是推算时间的函数
    public void happy_lcc(View view) throws ParseException
    {
        String begin=begin_time.getText().toString().trim();
        StringBuffer buffer=new StringBuffer(begin);
        int length_now=begin.length();

        if(length_now==0)
        {
            begin= LocalDate.now().format(DateTimeFormatter.ofPattern("yyyy-MM-dd")).toString().trim();
            buffer=new StringBuffer(begin);
            length_now=begin.length();  //获得输入框中内容的长度，以此来判断是否输入合法
        }

        if(length_now<8||length_now>10)
        {
                Toast.makeText(this,"输入错误,重新输入",Toast.LENGTH_SHORT).show();
                begin_time.setText("");
                return;
        }

        char c2=begin.charAt(4);

        if(c2=='-')
        {
            if(length_now==10)
            {
                if(begin.charAt(7)!='-')
                {
                    Toast.makeText(this,"输入错误,重新输入",Toast.LENGTH_SHORT).show();
                    begin_time.setText("");
                    return;
                }

            }
            SimpleDateFormat df = new SimpleDateFormat("yyyy-MM-dd");
            try {
                df.parse(begin);
            } catch (ParseException pe) {
                Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                begin_time.setText("");
                return;
            }
            if(length_now==8)
            {
                buffer.insert(5,0);
                buffer.insert(8,0);
            }
            else if(length_now==9)
            {
                if(begin.charAt(7)=='-')
                {
                    buffer.insert(8,0);
                }
                else {
                    buffer.insert(5,0);
                }
            }
            String begin1=new String(buffer);
            //////
            int begin_year=Integer.valueOf(begin1.substring(0,4)).intValue();
            int begin_month=Integer.valueOf(begin1.substring(5, 7)).intValue();
            int begin_day=Integer.valueOf(begin1.substring(8, 10)).intValue();
            if(begin_year%4==0&&begin_year%100!=0||begin_year%400==0)  //如果是闰月
            {
                if(begin_month>12)
                {
                    Toast.makeText(this, "月份输入错误,重新输入", Toast.LENGTH_SHORT).show();
                    begin_time.setText("");
                    return;
                }
                else
                {
                    if(begin_month==1||begin_month==3||begin_month==5||begin_month==7||begin_month==8||begin_month==10||begin_month==12)
                    {
                        if(begin_day>31)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                    if(begin_month==4||begin_month==6||begin_month==9||begin_month==11)
                    {
                        if(begin_day>30)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                    if(begin_month==2)
                    {
                        if(begin_day>29)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                }
            }
            else   //如果不是闰月
            {
                if(begin_month>12)
                {
                    Toast.makeText(this, "月份输入错误,重新输入", Toast.LENGTH_SHORT).show();
                    begin_time.setText("");
                    return;
                }
                else
                {
                    if(begin_month==1||begin_month==3||begin_month==5||begin_month==7||begin_month==8||begin_month==10||begin_month==12)
                    {
                        if(begin_day>31)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                    if(begin_month==4||begin_month==6||begin_month==9||begin_month==11)
                    {
                        if(begin_day>30)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                    if(begin_month==2)
                    {
                        if(begin_day>28)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                }

            }

            //////
            Date now_date = df.parse(begin1);
            String DAYS=all_days.getText().toString().trim();
            int day_length=DAYS.length();
            if(day_length==0)
            {
                Toast.makeText(this, "请输入天数", Toast.LENGTH_SHORT).show();
                return;
            }
            if((DAYS.charAt(0)=='-'||DAYS.charAt(0)=='+')&&day_length==1)
            {
                Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                return;
            }
            int days = Integer.parseInt(all_days.getText().toString());

            if(days>=0||days<0)
            {
                Calendar calendar = Calendar.getInstance();
                calendar.set(Integer.valueOf(begin1.substring(0, 4)).intValue(), Integer.valueOf(begin1.substring(5, 7)).intValue() - 1, Integer.valueOf(begin1.substring(8, 10)).intValue());
                calendar.add(Calendar.DAY_OF_YEAR, days);
                String result = new SimpleDateFormat("yyyy-MM-dd").format(calendar.getTime());
                Toast.makeText(MainActivity.this, result, Toast.LENGTH_SHORT).show(); //将选择的日期显示出来
            }
            else
            {
                Toast.makeText(this,"输入错误,重新输入",Toast.LENGTH_SHORT).show();
                return;
            }
        }
        else if(c2=='.')
         {
             if(length_now==10)
             {
                 if(begin.charAt(7)!='.')
                 {
                     Toast.makeText(this,"输入错误,重新输入",Toast.LENGTH_SHORT).show();
                     begin_time.setText("");
                     return;
                 }

             }
             SimpleDateFormat df = new SimpleDateFormat("yyyy.MM.dd");
             try {
                 df.parse(begin);
             } catch (ParseException pe) {
                 Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                 begin_time.setText("");
                 return;
             }
             if(length_now==8)
             {
                 buffer.insert(5,0);
                 buffer.insert(8,0);
             }
             else if(length_now==9)
             {
                 if(begin.charAt(7)=='.')
                 {
                     buffer.insert(8,0);
                 }
                 else {
                     buffer.insert(5,0);
                 }
             }
            String begin1 = new String(buffer);
            //////
            int begin_year=Integer.valueOf(begin1.substring(0,4)).intValue();
            int begin_month=Integer.valueOf(begin1.substring(5, 7)).intValue();
            int begin_day=Integer.valueOf(begin1.substring(8, 10)).intValue();
            if(begin_year%4==0&&begin_year%100!=0||begin_year%400==0)  //如果是闰月
            {
                if(begin_month>12)
                {
                    Toast.makeText(this, "月份输入错误,重新输入", Toast.LENGTH_SHORT).show();
                    begin_time.setText("");
                    return;
                }
                else
                {
                    if(begin_month==1||begin_month==3||begin_month==5||begin_month==7||begin_month==8||begin_month==10||begin_month==12)
                    {
                        if(begin_day>31)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                    if(begin_month==4||begin_month==6||begin_month==9||begin_month==11)
                    {
                        if(begin_day>30)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                    if(begin_month==2)
                    {
                        if(begin_day>29)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                }
            }
            else   //如果不是闰月
            {
                if(begin_month>12)
                {
                    Toast.makeText(this, "月份输入错误,重新输入", Toast.LENGTH_SHORT).show();
                    begin_time.setText("");
                    return;
                }
                else
                {
                    if(begin_month==1||begin_month==3||begin_month==5||begin_month==7||begin_month==8||begin_month==10||begin_month==12)
                    {
                        if(begin_day>31)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                    if(begin_month==4||begin_month==6||begin_month==9||begin_month==11)
                    {
                        if(begin_day>30)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                    if(begin_month==2)
                    {
                        if(begin_day>28)
                        {
                            Toast.makeText(this, "天数输入错误,重新输入", Toast.LENGTH_SHORT).show();
                            begin_time.setText("");
                            return;
                        }
                    }
                }

            }


            //////


            Date now_date = df.parse(begin1);
            String DAYS=all_days.getText().toString().trim();
            int day_length=DAYS.length();
            if(day_length==0)
            {
                Toast.makeText(this, "请输入天数", Toast.LENGTH_SHORT).show();
                return;
            }
            if((DAYS.charAt(0)=='-'||DAYS.charAt(0)=='+')&&day_length==1)
            {
                Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                return;
            }
            int days = Integer.parseInt(all_days.getText().toString());
            if(days>=0||days<0)
            {
                Calendar calendar = Calendar.getInstance();
                calendar.set(Integer.valueOf(begin1.substring(0, 4)).intValue(), Integer.valueOf(begin1.substring(5, 7)).intValue() - 1, Integer.valueOf(begin1.substring(8, 10)).intValue());
                calendar.add(Calendar.DAY_OF_YEAR, days);
                String result = new SimpleDateFormat("yyyy-MM-dd").format(calendar.getTime());
                Toast.makeText(MainActivity.this, result, Toast.LENGTH_SHORT).show(); //将选择的日期显示出来
            }
            else
            {
                Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
                return;
            }
        }
        else
        {
            Toast.makeText(this, "输入错误,重新输入", Toast.LENGTH_SHORT).show();
            begin_time.setText("");
            return;
        }

    }
}
