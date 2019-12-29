if ($time_iso8601 ~ '(\d{4}-\d{2}-\d{2})') {
        set $day $1;
    }
    access_log /data/wwwlogs/sms_nginx_$day.log combined;