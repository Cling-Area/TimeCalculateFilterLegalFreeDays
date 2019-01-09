//
//  ViewController.m
//  时间过滤周末及节假日
//
//  Created by tangmengze on 2019/1/4.
//  Copyright © 2019 tangmengze. All rights reserved.
//

#import "ViewController.h"

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    // Do any additional setup after loading the view, typically from a nib.
    [self dateStrNewFromNowAfterDays:7];
}

// 是否当月的最后一天
- (BOOL)isLastDayWith:(int)day forMonth:(int)month{
    NSString *year = @"2019";
    NSDateFormatter *format=[[NSDateFormatter alloc] init];
    [format setDateFormat:@"yyyy-MM-dd"];
    
    NSString *dateStr = [NSString stringWithFormat:@"%@-%02d-%02d", year, month, day];
    NSDate *newDate = [format dateFromString:dateStr];
    
   
    NSCalendar *calendar = [[NSCalendar alloc] initWithCalendarIdentifier:NSCalendarIdentifierGregorian];
    NSRange range = [calendar rangeOfUnit:NSCalendarUnitDay inUnit:NSCalendarUnitMonth forDate:newDate];
    
    
    
    return range.length == day;
}

// 当天是否为工作日 (排除放假安排跟周末)
- (BOOL)isDayWorkDayWith:(int)day forMonth:(int)month{
    // 2019放假安排
    NSArray<NSDictionary<NSString *, NSString *> *> *array = @[
                                                               @{},
                                                               @{
                                                                   @"1" : @"1", @"2" : @"0", @"3" : @"0", @"4" : @"0", @"5" : @"0", @"6" : @"0", @"7" : @"0",
                                                                   @"8" : @"0", @"9" : @"0", @"10" : @"0", @"11" : @"0", @"12" : @"0", @"13" : @"0", @"14" : @"0",
                                                                   @"15" : @"0", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   @"29" : @"0", @"30" : @"0", @"31" : @"0"
                                                                   }, // 一月
                                                               @{
                                                                   @"1" : @"0", @"2" : @"3", @"3" : @"3", @"4" : @"1", @"5" : @"1", @"6" : @"1", @"7" : @"1",
                                                                   @"8" : @"1", @"9" : @"1", @"10" : @"1", @"11" : @"0", @"12" : @"0", @"13" : @"0", @"14" : @"0",
                                                                   @"15" : @"0", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   }, // 二月
                                                               @{
                                                                   @"1" : @"0", @"2" : @"0", @"3" : @"0", @"4" : @"0", @"5" : @"0", @"6" : @"0", @"7" : @"0",
                                                                   @"8" : @"0", @"9" : @"0", @"10" : @"0", @"11" : @"0", @"12" : @"0", @"13" : @"0", @"14" : @"0",
                                                                   @"15" : @"0", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   @"29" : @"0", @"30" : @"0", @"31" : @"0"
                                                                   }, // 三月
                                                               @{
                                                                   @"1" : @"0", @"2" : @"0", @"3" : @"0", @"4" : @"0", @"5" : @"1", @"6" : @"1", @"7" : @"1",
                                                                   @"8" : @"0", @"9" : @"0", @"10" : @"0", @"11" : @"0", @"12" : @"0", @"13" : @"0", @"14" : @"0",
                                                                   @"15" : @"0", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   @"29" : @"0", @"30" : @"0"
                                                                   }, // 四月
                                                               
                                                               @{
                                                                   @"1" : @"1", @"2" : @"0", @"3" : @"0", @"4" : @"0", @"5" : @"0", @"6" : @"0", @"7" : @"0",
                                                                   @"8" : @"0", @"9" : @"0", @"10" : @"0", @"11" : @"0", @"12" : @"0", @"13" : @"0", @"14" : @"0",
                                                                   @"15" : @"0", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   @"29" : @"0", @"30" : @"0", @"31" : @"0"
                                                                   }, // 五月
                                                               @{
                                                                   @"1" : @"0", @"2" : @"0", @"3" : @"0", @"4" : @"0", @"5" : @"0", @"6" : @"0", @"7" : @"1",
                                                                   @"8" : @"1", @"9" : @"1", @"10" : @"0", @"11" : @"0", @"12" : @"0", @"13" : @"0", @"14" : @"0",
                                                                   @"15" : @"0", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   @"29" : @"0", @"30" : @"0"
                                                                   }, // 六月
                                                               @{
                                                                   @"1" : @"0", @"2" : @"0", @"3" : @"0", @"4" : @"0", @"5" : @"0", @"6" : @"0", @"7" : @"0",
                                                                   @"8" : @"0", @"9" : @"0", @"10" : @"0", @"11" : @"0", @"12" : @"0", @"13" : @"0", @"14" : @"0",
                                                                   @"15" : @"0", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   @"29" : @"0", @"30" : @"0", @"31" : @"0"
                                                                   }, // 七月
                                                               @{
                                                                   @"1" : @"0", @"2" : @"0", @"3" : @"0", @"4" : @"0", @"5" : @"0", @"6" : @"0", @"7" : @"0",
                                                                   @"8" : @"0", @"9" : @"0", @"10" : @"0", @"11" : @"0", @"12" : @"0", @"13" : @"0", @"14" : @"0",
                                                                   @"15" : @"0", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   @"29" : @"0", @"30" : @"0", @"31" : @"0"
                                                                   }, // 八月
                                                               
                                                               @{
                                                                   @"1" : @"0", @"2" : @"0", @"3" : @"0", @"4" : @"0", @"5" : @"0", @"6" : @"0", @"7" : @"0",
                                                                   @"8" : @"0", @"9" : @"0", @"10" : @"0", @"11" : @"0", @"12" : @"0", @"13" : @"1", @"14" : @"1",
                                                                   @"15" : @"1", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   @"29" : @"3", @"30" : @"0"
                                                                   }, // 九月
                                                               @{
                                                                   @"1" : @"1", @"2" : @"1", @"3" : @"1", @"4" : @"1", @"5" : @"1", @"6" : @"1", @"7" : @"1",
                                                                   @"8" : @"0", @"9" : @"0", @"10" : @"0", @"11" : @"0", @"12" : @"3", @"13" : @"0", @"14" : @"0",
                                                                   @"15" : @"0", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   @"29" : @"0", @"30" : @"0", @"31" : @"0"
                                                                   }, // 十月
                                                               @{
                                                                   @"1" : @"0", @"2" : @"0", @"3" : @"0", @"4" : @"0", @"5" : @"0", @"6" : @"0", @"7" : @"0",
                                                                   @"8" : @"0", @"9" : @"0", @"10" : @"0", @"11" : @"0", @"12" : @"0", @"13" : @"0", @"14" : @"0",
                                                                   @"15" : @"0", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   @"29" : @"0", @"30" : @"0"
                                                                   }, // 十一月
                                                               @{
                                                                   @"1" : @"0", @"2" : @"0", @"3" : @"0", @"4" : @"0", @"5" : @"0", @"6" : @"0", @"7" : @"0",
                                                                   @"8" : @"0", @"9" : @"0", @"10" : @"0", @"11" : @"0", @"12" : @"0", @"13" : @"0", @"14" : @"0",
                                                                   @"15" : @"0", @"16" : @"0", @"17" : @"0", @"18" : @"0", @"19" : @"0", @"20" : @"0", @"21" : @"0",
                                                                   @"22" : @"0", @"23" : @"0", @"24" : @"0", @"25" : @"0", @"26" : @"0", @"27" : @"0", @"28" : @"0",
                                                                   @"29" : @"0", @"30" : @"0", @"31" : @"0"
                                                                   }, // 十二月
                                                               ];
    NSString *year = @"2019";
    NSDateFormatter *format=[[NSDateFormatter alloc] init];
    [format setDateFormat:@"yyyy-MM-dd"];
    
    NSString *dateStr = [NSString stringWithFormat:@"%@-%02d-%02d", year, month, day];
    NSDate *newDate = [format dateFromString:dateStr];
    
    NSCalendar *calendar = [[NSCalendar alloc] initWithCalendarIdentifier:NSCalendarIdentifierGregorian];
    NSTimeZone* timeZone = [NSTimeZone timeZoneWithName:@"Asia/beijing"];
    [calendar setTimeZone: timeZone];
    
    NSCalendarUnit calendarUnit = NSCalendarUnitWeekday;
    NSDateComponents *theComponents = [calendar components:calendarUnit fromDate:newDate];
   
    
    NSArray *weekdays = [NSArray arrayWithObjects: [NSNull null], @"星期日", @"星期一", @"星期二", @"星期三", @"星期四", @"星期五", @"星期六", nil];
    NSString *dayStr = [weekdays objectAtIndex:theComponents.weekday];
//    NSLog(@"%@-%@", array[month][[NSString stringWithFormat:@"%d", day]], dayStr);
//    NSLog(@"%d--%d", !([dayStr isEqualToString:@"星期六"] || [dayStr isEqualToString:@"星期日"]), [array[month][[NSString stringWithFormat:@"%d", day]] isEqualToString:@"0"]);
    
    return [array[month][[NSString stringWithFormat:@"%d", day]] isEqualToString:@"3"] || (!([dayStr isEqualToString:@"星期六"] || [dayStr isEqualToString:@"星期日"]) && [array[month][[NSString stringWithFormat:@"%d", day]] isEqualToString:@"0"]);
}

// 过滤周末及法定节假日
- (NSString *)dateStrNewFromNowAfterDays:(NSInteger)days{
   
    NSDate *currentDate = [NSDate date];
    
//    NSTimeInterval oneDay = 24 * 60 * 60;
//    NSDate *testDate = [currentDate initWithTimeIntervalSinceNow: 1 * oneDay];
//    currentDate = testDate;
    
    NSCalendar *calendar = [[NSCalendar alloc] initWithCalendarIdentifier:NSCalendarIdentifierGregorian];
    NSTimeZone* timeZone = [NSTimeZone timeZoneWithName:@"Asia/beijing"];
    [calendar setTimeZone: timeZone];
    NSCalendarUnit calendarUnit = NSCalendarUnitWeekday | NSCalendarUnitYear | NSCalendarUnitMonth | NSCalendarUnitDay;
    NSDateComponents *theComponents = [calendar components:calendarUnit fromDate:currentDate];
    NSString *month = [NSString stringWithFormat:@"%ld", theComponents.month];
    NSString *day = [NSString stringWithFormat:@"%ld", theComponents.day];
    
    
    int dayAddTotal = 0;
    int workDayAddNow = 7;

    // 当前多少号
    int currentDay = day.intValue;
    // 当前月份
    int currentMonth = month.intValue;
    
    // 累加工作日不足七天
    while(workDayAddNow > 0) {
        
        // 是否当月最后一天
        BOOL isLastDay = NO;
        if ([self isLastDayWith:currentDay forMonth:currentMonth]) {
            // 从下一个月开始累加
            currentDay = 1;
            currentMonth += 1;
            isLastDay = YES;
        }
        if (!isLastDay) {
            currentDay ++;
        }
        
        // 从今天开始累加七天工作日最终需要多少天
        BOOL isWorkDay = [self isDayWorkDayWith:currentDay forMonth:currentMonth];
        if(isWorkDay){ // 工作日
            // 第一天
            workDayAddNow --;
            NSLog(@"%d--工作日", currentDay);
        }else{ // 非工作日
            NSLog(@"%d--非工作日", currentDay);
        }
        
        dayAddTotal ++;
        
    }
    
    NSDateFormatter *formatter = [[NSDateFormatter alloc]init];
    [formatter setDateFormat:@"YYYY-MM-dd"];
    
    NSDateComponents *adcomps = [[NSDateComponents alloc] init];
    [adcomps setYear:0];
    [adcomps setMonth:0];
    [adcomps setDay:dayAddTotal];
    NSDate *newdate = [calendar dateByAddingComponents:adcomps toDate:currentDate options:0];
    NSString *dateStr = [formatter stringFromDate:newdate];
    NSString *finalDateStr = [NSString stringWithFormat:@"%@ 23:59:59", dateStr];
    NSLog(@"%@", finalDateStr);
    return finalDateStr;
}


// 过滤周末两天的N天后
- (NSString *)dateStrFromNowAfterDays:(NSInteger)days{
    NSDate *currentDate = [NSDate date];
    int daysAdd = 0;
    
    NSCalendar *calendar = [[NSCalendar alloc] initWithCalendarIdentifier:NSCalendarIdentifierGregorian];
    NSTimeZone* timeZone = [NSTimeZone timeZoneWithName:@"Asia/beijing"];
    [calendar setTimeZone: timeZone];
    NSCalendarUnit calendarUnit = NSCalendarUnitWeekday;
    NSDateComponents *theComponents = [calendar components:calendarUnit fromDate:currentDate];
    
    NSArray *weekdays = [NSArray arrayWithObjects: [NSNull null], @"星期日", @"星期一", @"星期二", @"星期三", @"星期四", @"星期五", @"星期六", nil];
    NSString *dayStr = [weekdays objectAtIndex:theComponents.weekday];
    if ([dayStr isEqualToString:@"星期一"] || [dayStr isEqualToString:@"星期二"] || [dayStr isEqualToString:@"星期三"]) { // 星期一 星期二 星期三
        daysAdd = 2;
    }else if ([dayStr isEqualToString:@"星期四"] || [dayStr isEqualToString:@"星期五"]){ // 星期四 星期五 星期六
        daysAdd = 4;
    }else if([dayStr isEqualToString:@"星期六"]){
        daysAdd = 3;
    }else if([dayStr isEqualToString:@"星期日"]){ // 星期日
        daysAdd = 2;
    }
    days += daysAdd;
    
    NSDateFormatter *formatter = [[NSDateFormatter alloc]init];
    [formatter setDateFormat:@"YYYY-MM-dd"];
    
    NSDateComponents *adcomps = [[NSDateComponents alloc] init];
    [adcomps setYear:0];
    [adcomps setMonth:0];
    [adcomps setDay:days];
    NSDate *newdate = [calendar dateByAddingComponents:adcomps toDate:currentDate options:0];
    NSString *dateStr = [formatter stringFromDate:newdate];
    NSLog(@"%@", dateStr);
    return dateStr;
}
@end
